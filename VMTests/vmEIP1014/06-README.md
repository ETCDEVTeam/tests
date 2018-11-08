#### create2_6: Derivation of expected gas values.

| Bytecode | Opcode Assembly |   Gas | Notes                                                                              |
|      --- | ---             |   --- | ---                                                                                |
|       60 | PUSH1 0x0       |     3 |                                                                                    |
|       35 | CALLDATALOAD    |     3 | `"data": "0x"`, so `CALLDATALOAD` causes a zero-value to be pushed onto the stack. |
|       60 | PUSH1 0x0       |     3 |                                                                                    |
|       52 | MSTORE          |     6 |                                                                                    |
|       60 | PUSH1 0x0       |     3 |                                                                                    |
|       60 | PUSH1 0x0       |     3 |                                                                                    |
|       60 | PUSH1 0x0       |     3 |                                                                                    |
|       60 | PUSH1 0x0       |     3 |                                                                                    |
|       f5 | CREATE2         | 32000 |                                                                                    |
|       60 | PUSH1 0x0       |     3 |                                                                                    |
|       55 | SSTORE          | 20000 |                                                                                    |

Total: 52030
