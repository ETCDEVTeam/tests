#### create2_0: Derivation of expected gas values.

| Bytecode | Opcode Assembly          |   Gas | Notes |
|      --- | ---                      |   --- |       |
|     6000 | PUSH1 0x00               |     3 |       |
|     6001 | PUSH1 0x01               |     3 |       |
|     6000 | PUSH1 0x00               |     3 |       |
|     6000 | PUSH1 0x00               |     3 |       |
|       f5 | CREATE2                  | 32009 | 32000 + 2*( SHA3wordcost=3 ) + 3*( 1 word mem expansion) |
|     6000 | PUSH1 0x00               |     3 |       |
|       55 | SSTORE                   | 20000 |       |

Total: 52024

