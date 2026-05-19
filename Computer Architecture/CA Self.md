## Von Neumann Architecture
Von Neumann Architecture is made out of 4 core elements
- CPU
- Memory
- I/O
- Bus
## Boolean Algebra
![[Pasted image 20250507141506.png]]
### Karnaugh Maps
https://www.youtube.com/watch?v=RO5alU6PpSU
And for (Don't cares) which is important:
https://www.youtube.com/watch?v=bW3Vg7paRBs
## 4 Bit Adder (RCA)
### Full Adder
![[Pasted image 20250505230052.png]]
Full Adder takes 2 bits A and B, and also takes another bit for Carry In. And then it outputs 1 bit for the result (S), and one Carry Out.
### 4 Bit Adder
![[Pasted image 20250505230432.png]]
With 4 Full Adders you can make a 4 bit adder like this.
This design is also called *Ripple carry adder*
### Critical Path
In a ripple carry adder, the critical path is ==the longest delay from input to output==, which occurs when carries propagate through all the full adders in the chain. This delay is directly proportional to the number of bits in the adder.