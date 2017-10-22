# Computer Architecture Project2 -- Stage3

### 小组成员
勾凌睿: [CA_P2_S3_Go](https://github.com/Lingrui98/CA_P2_S3_Go)

吴嘉皓: [CA_P2_S3_Wu](https://github.com/framywhale/CA_P2_S3_Wu)

### 实验要求：
1. 在**实验一**（[勾凌睿](https://github.com/Lingrui98/CA_P2_S1)、[吴嘉皓](https://github.com/framywhale/CA-Project02_Stage01)）和实验二（[勾凌睿](https://github.com/Lingrui98/CA_P2_S2_Go)、[吴嘉皓](https://github.com/framywhale/CA_P2_S3_Wu)）的基础上，增加15条指令：**DIV、DIVU、MULT、MULTU、MFHI、MFLO、MTHI、MTLO、BGEZ、BGTZ、BLEZ、BLTZ、BLTZAL、BGEZAL、JALR**
2. 具体描述，参见勾凌睿的[README](https://github.com/Lingrui98/CA_P2_S3_Go)

### （阶段三） 32位五级流水的MPIS处理器数据通路图：（暂为）

![Datapath_version2.3](https://github.com/framywhale/CA_P2_S3_Wu/blob/master/Datapath_version2.3.PNG)

### 控制信号（Stage3）

| Inst  | Opcode |  Func  | RegWrite | RegDst | MemWrite| MemEn |MemToReg| ALUSrcA | ALUSrcB|PCSrc|JSrc | ALUOp |
|:-:    | :-:    |:-:     |:-:       |:-:     | :-:     |:-:    |:-:     |:-:      |:-:     |:-:  |:-:  |:-:    |
| ADDI  | 001000 |    X   |   1111   |   00   |   0000  |   0   |   0    |    00   |   01   |  00 |  0  |  0010 |
| ANDI  | 001100 |    X   |   1111   |   00   |   0000  |   0   |   0    |    00   |   01   |  00 |  0  |  0000 |
| ORI   | 001101 |    X   |   1111   |   00   |   0000  |   0   |   0    |    00   |   11   |  00 |  0  |  0001 |
| XORI  | 001110 |    X   |   1111   |   00   |   0000  |   0   |   0    |    00   |   11   |  00 |  0  |  1010 |
| ADD   | R-Type | 100000 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0010 |
| SUB   | R-Type | 100010 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0110 |
| SUBU  | R-Type | 100011 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1000 |
| SLTU  | R-Type | 101011 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0100 |
| AND   | R-Type | 100100 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0000 |
| NOR   | R-Type | 100111 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1001 |
| XOR   | R-Type | 100110 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1010 |
| SLLV  | R-Type | 000100 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0101 |
| SRA   | R-Type | 000011 |   1111   |   01   |   0000  |   0   |   0    |    10   |   00   |  00 |  0  |  1011 |
| SRAV  | R-Type | 000111 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1011 |
| SRL   | R-Type | 000010 |   1111   |   01   |   0000  |   0   |   0    |    10   |   00   |  00 |  0  |  1100 |
| SRLV  | R-Type | 000110 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1100 |
