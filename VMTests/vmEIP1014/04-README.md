#### create2_4: Derivation of expected gas values.

> Note: `init_code` as spec'd in EIP-1014.md is `deadbeef`. This is invalid bytecode, and will fail
when passed thru an actual EVM. Therefore these tests have substituted valid bytecode `60de60ad` as `init_code` instead.
If the VM test runner environment also executes the `init_code` as a created account,
expected gas cost is 52039 (canonical += 6, where 6 = 2\*(PUSH1=3)).

| Bytecode | Opcode Assembly                                                           |   Gas | Notes                                                   |
|      --- | ---                                                                       |   --- |                                                         |
|     6000 | PUSH4 0x60de60ad                                                          |     3 |                                                         |
|     6000 | PUSH1 0x0                                                                 |     3 |                                                         |
|       52 | MSTORE                                                                    |     6 | Stores as int256==32bit                                 |
|     6000 | PUSH32 0x00000000000000000000000000000000000000000000000000000000cafebabe |     3 |                                                         |
|     6001 | PUSH1 0x4                                                                 |     3 |                                                         |
|     6000 | PUSH1 0x1c                                                                |     3 |                                                         |
|     6000 | PUSH1 0x0                                                                 |     3 |                                                         |
|       f5 | CREATE2                                                                   | 32006 | 32000 + 1*( SHA3wordcost=3 ) (mem already using 1 word) |
|     6000 | PUSH1 0x00                                                                |     3 |                                                         |
|       55 | SSTORE                                                                    | 20000 |                                                         |

Total: 52033
