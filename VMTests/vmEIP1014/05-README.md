#### create2_5: Derivation of expected gas values.

> Note: While `05.json` does as spec'd in EIP1014 (using `deadbeef...deadbeef`) as `init_code`, `05_custom.json** uses instead runnable bytecode.

| Bytecode | Opcode Assembly      |   Gas | Notes                    |
|      --- | ---                  |   --- | ---                      |
|       60 | PUSH1 0x0            |     3 |                          |
|       35 | CALLDATALOAD         |     3 |                          |
|       60 | PUSH1 0x0            |     3 |                          |
|       52 | MSTORE               |     6 |                          |
|       60 | PUSH1 0x20           |     3 |                          |
|       35 | CALLDATALOAD         |     3 |                          |
|       60 | PUSH1 0x20           |     3 |                          |
|       52 | MSTORE               |     6 |                          |
|       7f | PUSH32 0x0..cafebabe |     3 |                          |
|       60 | PUSH1 0x2c           |     3 | 0x2c==44==length of data |
|       60 | PUSH1 0x0            |     3 |                          |
|       60 | PUSH1 0x0            |     3 |                          |
|       f5 | CREATE2              | 32012 |                          |
|       60 | PUSH1 0x0            |     3 |                          |
|       55 | SSSTORE              | 20000 |                          |

Total: 52057

**`05_custom.json`'s runnable `init_code`:**

```
PUSH1 0xde
PUSH1 0xad
PUSH1 0xbe
PUSH1 0xef
SWAP1
SWAP2
SWAP3
POP
POP
POP
POP
PUSH1 0xde
PUSH1 0xaf
SWAP1
POP
POP
PUSH1 0xde
PUSH1 0xad
PUSH1 0xbe
PUSH1 0xef
SWAP1
SWAP2
SWAP3
POP
POP
POP
POP
PUSH1 0xfe
PUSH1 0xed
SWAP1
POP
POP
```

