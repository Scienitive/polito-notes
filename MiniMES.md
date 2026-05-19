![[Pasted image 20260323125502.png]]
- What does the number section do in Machine Department section?

- What does external code mean in the production order section?

### As a user
- I'd like to have the option to update the values like "unit measure" or "raw material" without refreshing the page and losing all previous values I entered.

# SmartEDGE
- System continuously gathers data. In case of a crash or power loss it can automatically resume from it's last valid state. It can also gather data locally when the cloud connection is lost.
- The software can be dynamically reconfigured (changing IPs, protocols, or logic) via a web interface without needing a manual restart
## Five Core Modules
- **Protocol:** The base module that manages the actual connection, reading, and writing to the specific machine protocol
	- (not sure about this one that much)
- **Sampler:** Periodically connects to the machine, reads raw data and stores it in the local *Raw_Data* table in the database
	- why do we need this? is this how we get the data from machines all the time or is it something like a backup?
- **Logicator:** A standalone thread that manages the "Tracking Variables" section. It pulls raw data from database, applies the mathematical and logical rules that has been defined. Saves the result to the *Information _Data* table in the database. And it deletes the raw data.
	- So if it deletes the raw data I'm assuming that we try to avoid raw data as much as possible because it's messy/not formatted well.
- **Sender:** This is an important one for me! Retrieves processed "Tracking Variables" and sends them to the SmartHinge cloud via *HTTP*. It handles backups if cloud is offline.
	- I wonder what payload does it use (JSON / plain text / Protobuf)? I've heard that for internal communication like this Protobuf is an excellent choice.
- **Writer:** A watcher thread that listens for new *.json* recipe files sent from cloud. When a file appears, it connects to the machine, writes the new parameters, and then deletes the file

## Configuration and Database
The EDGE uses *SQLAlchemy Database* to store the machine data (*Raw_Data*, *Information_Data*) as well as the entire system configuration data.
### What is SQLAlchemy?
SQLAlchemy is not a competitor to PostgreSQL, MySQL or SQLite. It's a tool that works with them.
SQLAlchemy is a *Python Library* known as ORM and a SQL toolkit.
- So instead of writing `SELECT * FROM users WHERE age > 20;` you write `session.query(User).filter(User.age > 20).all()` just like Prisma or DrizzleORM.
- It's database independent. Different databases have slightly different flavors of SQL, This ORM makes you write for each of them.

**NOTE FROM ALTUG:** I'm kinda surprised to see a choice like this. To me this feels like additional dependency. I'm sure it makes things convenient but if you're using ORM you're kinda limited to what ORM can offer. Especially in terms of speed.
## EdgeDashboard
Edge includes a built-in Vue 3 web application (nice!).
- It supports multiple languages
- User login
- Import/Export JSON configs
Through this dashboard users can:
- Add machines
- Define reading/writing variables
- Construct logic formulas for Tracking Variables. Using [Google Blockly](https://developers.google.com/blockly)
- View real-time machine logs
**QUESTION FROM ALTUG:** 
![[Pasted image 20260324152644.png]]
This part seems weird to me. We're making a lot of sending / deleting in databases but the data never leaves the internal system in the end (meaning EdgeDashboard and SmartHinge). So instead of "sending this data" can't SmartHinge just retrieve the data from EdgeDashboards database?
![[Pasted image 20260324160226.png]]
We already have one database? Or is this representation just or Edge and doesn't cover SmartHinge

![[Pasted image 20260324162838.png]]
Isn't there a bug here?
Partial Counter -> 10
We check and store the value = 10
Partial Counter resets -> 0
Partial Counter keeps continuing working...
Partial Counter -> 20
We check, We say since the new value is bigger than last the difference is the actual count so 10 is the result
But we missed the reset and the real answer was 20
But maybe this bug is impossible because we check it very frequently or something like that?

![[Pasted image 20260324164737.png]]
These types of tables work but services like Redis are invented to solve this kind of issue. So maybe there could be some benefits to use Redis or something similar.

# Source Code of MiniMES
## Controller
```
A little typo: smartshare-minimes/backend/src/main/java/com/orchestraweb/smartshare/controller/machine/MachineController.java / line:219 / Close should be clone
```


Below are for documentation:
@Operation
@ApiResponses - @ApiResponse
@Parameter

@RequestParam => This is for searchParams => `?pageNo=2&pageSize=10`

@PathVariable => Responsible for filling variables from URL Path:
For example: `@GetMapping(value = "/{imei}")` if you have this you need:
`@PathVariable(value = "imei")` to capture as a variable.

@RequestBody => Parses the incoming Post requests body section and formats it into Java Object from JSON. It generally uses a library called Jackson for this purpose.

@Valid => Validates the incoming JSON to the expected Java Class that we've assigned. It checks all the conditions like @Min, @NotNull... and expect them to be valid
Also it checks Inheritance Validation as well for example:
```
public class MachineDto extends MachineRefDto
```
In this case if you have other necessities on MachineRefDto they're also checked.
If you use @Valid on Class implementation on a variable:
```
@Valid // <-- CASCADING VALIDATION
@JsonProperty("machine_childs")
private List<MachineDto> machineChilds;
```
This means cascading validation. So every machineChild is also getting checked.

@PreAuthorize => Before your controller code executes, Spring creates a proxy and it hits there first. This proxy uses *SpEL (Spring Expression Language)* and has several built-in functions. PreAuthorize is used for security checks before allowing the request to continue.

### The "Translation" Pipeline (not %100 accurate for this repository maybe)

To understand where your tools (**Jackson** and **ModelMapper**) fit in, think of a pipeline. When data comes into your API, it goes through two distinct translations:
##### 1. Crossing the Border: JSON ↔ DTO (Handled by Jackson)

When an HTTP request hits your server, it arrives as a raw JSON string. Spring Boot uses the **Jackson** library behind the scenes (triggered by `@RequestBody` or `@ResponseBody`). Jackson reads the JSON text and constructs a Java DTO out of it.
- _Analogy:_ Jackson is the customs agent at the border translating a foreign language (JSON) into your application's native language (Java DTO).
##### 2. Moving Inside the App: DTO ↔ Entity (Handled by ModelMapper)

Once the data is a Java DTO, your Controller passes it to your Service layer. But your database doesn't want a DTO; it wants a Database Entity (e.g., a `Machine` class annotated with `@Entity`). This is where **ModelMapper** comes in. It takes the data from your DTO and copies it over to your Entity object.

- _Analogy:_ ModelMapper is the factory worker moving parts from the receiving box (DTO) to the actual assembly line (Entity).
#### Summary of the Flow (Incoming POST Request)

1. **Client:** Sends **JSON** text over the internet.
2. **Spring/Jackson:** Converts JSON text ➡️ **DTO** (Java Object).
3. **Controller:** Validates the **DTO** (`@Valid`).
4. **Service/ModelMapper:** Maps **DTO** ➡️ **Entity** (Java Object).
5. **Repository:** Saves the **Entity** to the Database.

When you send data _out_ (a GET request), the process runs exactly in reverse!


## Specifications
I don't understand that part.

Machine.java vs MachineDTO.java => Why are they have to be different?
![[Pasted image 20260325170720.png]]
I think converters are responsible from
Machine Entity <==> Machine DTO
I don't exactly understand the need for DTO I suppose.


Timefold
n+1 database problem
