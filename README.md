# Computer Architecture Project2 -- Stage3

### 小组成员
勾凌睿: [CA_P2_S3_Go](https://github.com/Lingrui98/CA_P2_S3_Go)

吴嘉皓: [CA_P2_S3_Wu](https://github.com/framywhale/CA_P2_S3_Wu)

### 实验要求：
1. 在**实验一**（[勾凌睿](https://github.com/Lingrui98/CA_P2_S1)、[吴嘉皓](https://github.com/framywhale/CA-Project02_Stage01)）和实验二（[勾凌睿](https://github.com/Lingrui98/CA_P2_S2_Go)、[吴嘉皓](https://github.com/framywhale/CA_P2_S3_Wu)）的基础上，增加15条指令：**DIV、DIVU、MULT、MULTU、MFHI、MFLO、MTHI、MTLO、BGEZ、BGTZ、BLEZ、BLTZ、BLTZAL、BGEZAL、JALR**
2. 具体描述，参见勾凌睿的[README](https://github.com/Lingrui98/CA_P2_S3_Go)

### （阶段三） 32位五级流水的MPIS处理器数据通路图：（暂为）

![Datapath_version2.0](https://github.com/framywhale/CA_P2_S2_Wu/blob/master/Datapath_version2.0.PNG)

### 控制信号（Stage3）

| Inst  | Opcode |  Func  | RegWrite | RegDst | MemWrite| MemEn |MemToReg| ALUSrcA | ALUSrcB|PCSrc|JSrc | ALUOp |
|:-:    | :-:    |:-:     |:-:       |:-:     | :-:     |:-:    |:-:     |:-:      |:-:     |:-:  |:-:  |:-:    |
| BGEZ  | 000001 |    X   |   0000   |   00   |   0000  |   0   |   0    |    00   |   00   |  10 |  0  |  0000 |
| BGTZ  | 000111 |    X   |   0000   |   00   |   0000  |   0   |   0    |    00   |   00   |  10 |  0  |  0000 |
| BLEZ  | 000110 |    X   |   0000   |   00   |   0000  |   0   |   0    |    00   |   00   |  10 |  0  |  0000 |
| BLTZ  | 000001 |    X   |   0000   |   00   |   0000  |   0   |   0    |    00   |   00   |  10 |  0  |  0000 |
| BGEZAL| 000001 |    X   |   1111   |   11   |   0000  |   0   |   0    |    00   |   00   |  10 |  0  |  0000 |
| BLTZAL| 000001 |    X   |   1111   |   11   |   0000  |   0   |   0    |    00   |   00   |  10 |  0  |  0000 |
| JALR  | R-Type | 001001 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  01 |  1  |  0000 |
| MULT  | R-Type | 011000 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0100 |
| MULTU | R-Type | 011001 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0000 |
| DIV   | R-Type | 011010 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1001 |
| DIVU  | R-Type | 011011 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1010 |
| MFHI  | R-Type | 010000 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  0101 |
| MFLO  | R-Type | 010010 |   1111   |   01   |   0000  |   0   |   0    |    10   |   00   |  00 |  0  |  1011 |
| MTHI  | R-Type | 010001 |   1111   |   01   |   0000  |   0   |   0    |    00   |   00   |  00 |  0  |  1011 |
| MTLO  | R-Type | 010011 |   1111   |   01   |   0000  |   0   |   0    |    10   |   00   |  00 |  0  |  1100 |
