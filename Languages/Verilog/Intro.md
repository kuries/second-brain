#### Structural:
- all the statements are executed concurrently.
- in the always block and the initial begin block, the statements are executed sequentially.
---
#### Data Flow:
- Here instead of mentioning the gate names `and, xor, or` we use the symbols directly `&, ^, |`
 
---

#### Behavioural:
- 
---

#### General:
- to run the code, 
```verilog
iverilog -o output_file module.v test_bench.v

vvp output_file

gtkwave	ha1.vcd //this is mentioned in a dumpfile in verilog testbench
```
- so as to avoid mentioning the main module while compiling along with the testbench file we can just include the main module in the test bench this way
```verilog
`include "module.v"`
```
- Only register variables are allowed inside always blocks

![[Pasted image 20210818171139.png]]

![[Pasted image 20210824215350.png]]