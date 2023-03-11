# bcpu
### bcpu instruction set architechture tables
#### compute
`1111a c1 c2 c3 c4 c5 c6 d1 d2 d3 j1 j2 j3`
```
111 fixed opcode for compute, a whether computation performed on memory location
addressed by A register (a=1) or the value in the register (a=0)
```
---
compute
|ALU Operation | c1 | c2 | c3 | c4 | c5 | c6 |
|--------------|----|----|----|----|----|----|
|0             | 1  | 1  | 1  | 0  | 1  | 0  |
|1             | 1  | 1  | 1  | 0  | 1  | 1  |
|-1            | 1  | 1  | 1  | 1  | 0  | 0  |
|D             | 0  | 0  | 1  | 1  | 0  | 0  |
|A             | 1  | 1  | 0  | 0  | 0  | 0  |
|!D            | 0  | 0  | 1  | 1  | 0  | 1  |
|!A            | 1  | 1  | 0  | 0  | 0  | 1  |
|-D            | 0  | 0  | 1  | 1  | 1  | 1  |
|-A            | 1  | 1  | 0  | 0  | 1  | 1  |
|D+1           | 0  | 1  | 1  | 1  | 1  | 1  |
|A+1           | 1  | 1  | 0  | 1  | 1  | 1  |
|D-1           | 0  | 0  | 1  | 1  | 1  | 0  |
|A-1           | 1  | 1  | 0  | 0  | 1  | 0  |
|D+A           | 0  | 1  | 0  | 0  | 1  | 0  |
|D-A           | 0  | 0  | 0  | 1  | 1  | 0  |
|A-D           | 0  | 1  | 0  | 0  | 1  | 1  |
|D&A           | 0  | 0  | 0  | 0  | 1  | 0  |
|D\|A          | 0  | 1  | 0  | 1  | 0  | 1  |
|not used      | 0  | 0  | 0  | 0  | 0  | 0  |

dest

|Mnemonic|d1|d2|d3|
|--------|--|--|--|
|null    | 0| 0| 0|
|M       | 0| 0| 1|
|D       | 0| 1| 0|
|MD      | 0| 1| 1|
|A       | 1| 0| 0|
|AM      | 1| 0| 1|
|AD      | 1| 1| 0|
|AMD     | 1| 1| 1|

jump cond
| Jump Condition | j1 | j2 | j3 |
|----------------|----|----|----|
| null           | 0  | 0  | 0  |
| JGT            | 0  | 0  | 1  |
| JEQ            | 0  | 1  | 0  |
| JGE            | 0  | 1  | 1  |
| JLT            | 1  | 0  | 0  |
| JNE            | 1  | 0  | 1  |
| JLE            | 1  | 1  | 0  |
| JMP            | 1  | 1  | 1  |
