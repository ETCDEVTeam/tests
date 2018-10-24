
#### create2_0: Derivation of expected gas values.

| Bytecode | Opcode Assembly          |   Gas |
|      --- | ---                      |   --- |
|     6000 | PUSH1 0x00               |     3 |
|     6001 | PUSH1 0x01               |     3 |
|     6000 | PUSH1 0x00               |     3 |
|     6000 | PUSH1 0x00               |     3 |
|       f5 | CREATE2                  | 32006 |
|        - | [mem expansion * 1 word] |     3 |
|     6000 | PUSH1 0x00               |     3 |
|       55 | SSTORE                   | 20000 |

Total: 52024

