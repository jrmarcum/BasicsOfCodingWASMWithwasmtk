#### Go's `fmt` verbs are replaced by template literals and manual formatting helpers. Exponential notation (`1.234000e+08`) is hard-coded since wasic has no `toExponential`; `typeof` is replaced with the string `"struct"`.
___
##### Run Command:

`$ wasmtk run string-formatting.ts`

##### Results:

`{1 2}`
`{x:1 y:2}`
`{x:1, y:2}`
`struct`
`true`
`123`
`1110`
`!`
`1c8`
`78.900000`
`1.234000e+08`
`1.234000E+08`
`"string"`
`"string"`
`6865782074686973`
`|    12|   345|`
`|  1.20|  3.45|`
`|1.20  |3.45  |`
`|   foo|     b|`
`|foo   |b     |`
`a string`
`an error`

___

##### Run Command:

`$ wasmtk wasic string-formatting.ts`

`$ wasmtk run string-formatting.wasm`

##### Results:

`{1 2}`
`{x:1 y:2}`
`{x:1, y:2}`
`struct`
`true`
`123`
`1110`
`!`
`1c8`
`78.900000`
`1.234000e+08`
`1.234000E+08`
`"string"`
`"string"`
`6865782074686973`
`|    12|   345|`
`|  1.20|  3.45|`
`|1.20  |3.45  |`
`|   foo|     b|`
`|foo   |b     |`
`a string`
`an error`

___

##### Run Command:

`$ wasmtk info string-formatting.wasm`
