#### WebAssembly dynamic arrays grow via `push`. Strings format using Go's space-separated bracket notation `[a b c]`; an empty-string slice of length 3 prints as `[  ]` (three empty strings with spaces).
___
##### Run Command:

`$ wasmtk run slices.ts`

##### Results:

`emp: [  ]`
`set: [a b c]`
`get: c`
`len: 3`
`apd: [a b c d e f]`
`cpy: [a b c d e f]`
`sl1: [c d e]`
`sl2: [a b c d e]`
`sl3: [c d e f]`
`dcl: [g h i]`
`2d: [[0] [1 2] [2 3 4]]`

___

##### Run Command:

`$ wasmtk wasic slices.ts`

`$ wasmtk run slices.wasm`

##### Results:

`emp: [  ]`
`set: [a b c]`
`get: c`
`len: 3`
`apd: [a b c d e f]`
`cpy: [a b c d e f]`
`sl1: [c d e]`
`sl2: [a b c d e]`
`sl3: [c d e f]`
`dcl: [g h i]`
`2d: [[0] [1 2] [2 3 4]]`

___

##### Run Command:

`$ wasmtk info slices.wasm`
