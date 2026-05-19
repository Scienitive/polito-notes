## Von Neumann Architecture
Von Neumann Architecture is made out of 4 core elements
- CPU
- Memory
- I/O
- Bus
## Basic Logic Operators
![[Pasted image 20250505225441.png]]
## Design Of 4 Bit Adder
### Full Adder
![[Pasted image 20250505230052.png]]
Full Adder takes 2 bits A and B, and also takes another bit for Carry In. And then it outputs 1 bit for the result (S), and one Carry Out.
### 4 Bit Adder
![[Pasted image 20250505230432.png]]
With 4 Full Adders you can make a 4 bit adder like this.
This design is also called *Ripple carry adder*
### Critical Path
...
## Karnaugh Maps
For optimizing a boolean algorithm.
In order to use it you need at most 4 inputs. More than 4, it's not usable.
## 2's Complement Marker
Positive + Positive = Positive
Negative + Negative = Negative
You should only care about these two situations for detecting overflow on 2's complement.
## Adder/Subtractor
![[Pasted image 20250506005224.png]]
## Carry Lookahead Adder
### Area of Carry Computation Block
![[Pasted image 20250506180238.png]]
**!!! It is very big**
## Fan/In - Fan/Out
### Fan/In
*How many inputs at most can be accepted by a real gate*
The answer is **4**

So if you want to make an XOR with 7 inputs you can do it this way:
![[Pasted image 20250506182256.png]]
### Fan/Out
*How many inputs can be driven by a single input line*
When you split the inputs their current will be half so at some point the signal strength will be very low.
The answer is **4**

To solve this issue we can use so called *Boosters* but they will add delay and area to the component.
![[Pasted image 20250506184518.png]]

So Carry Lookahead Adders are faster in theory but if they become very large they become almost as slow and perhaps slower than Ripple Carry Adders.
The important number here is **8**
**8 bit** Carry Lookahead Adders and less are faster and comes with advantages but more than 8 bit then the disadvantages surpass the advantages.
Roughly the expected delay is:
$$
t_{CLA_N} \approx log_{2}(N) \cdot t_{FA}
$$
Where
- $N$ is the number of bits.
- $t_{CLA_N}$ is delay of Carry Lookahead Adder
- $t_{FA}$ is delay of Ripple Carry Adder
![[Pasted image 20250506185547.png]]
## Carry Propagate Adder
Much like Ripple Carry Adder. Faster but more costly in terms of area. However unlike CLA the grow is linear instead of exponential.
## Combinational Circuits / Sequential Circuits
![[Pasted image 20250506225349.png]]
## SR Flip Flop / JK Flip Flop
https://www.youtube.com/watch?v=AaN72s5WfOM&list=PLuYnCh-Sh1XdvuSGjQRi2jgUH9_CiVR8J
## Edge Clock / Level Clock
## D Flip Flop (Memory Cell)
## T Flip Flop
## Asynchronous Counter
## Multiplexer
![[Pasted image 20250507004052.png]]
It's like a traffic light. Also known as *Selector*.
## Hard Enable / Soft Enable
### Hard Enable
![[Pasted image 20250507005215.png]]
Physically disconnecting all but one components ability to write to BUS.
### Soft Enable
![[Pasted image 20250507005508.png]]
Here we are not physically disconnecting the components but we are forcing all but one components write section to 0 (or any other defined value).
## Decoder
![[Pasted image 20250507005830.png]]
## Encoder
Performs the reverse action of decoder.
However just by reversing the input and output for the decoder you can't turn it into an encoder.
## Binary Comparator
![[Pasted image 20250507011055.png]]
## Registers
![[Pasted image 20250507095656.png]]
## Synchronous Counter
## Serial Adder
![[Pasted image 20250507100743.png]]
![[Pasted image 20250507101241.png]]
### Comparison Between SA / RCA / CLA
![[Pasted image 20250507101051.png]]
### Shift Register
![[Pasted image 20250507101355.png]]
So basically a register that also operates *>>* or *<<* after getting a new value.
### Practical Usage of Serial Adders
![[Pasted image 20250507102507.png]]
They need Shift registers on both sides.
## State Machine
State Machine = Circuits with Memory = Sequential Circuits
![[Pasted image 20250507102647.png]]
## Creating a Circuit For a Problem
At the end of CA06.mp4 there is a very nice section for showing this.
## Memory
![[Pasted image 20250507120945.png]]