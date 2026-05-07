#### WebAssembly arrays are numeric typed allocations in linear memory. Output uses Go's space-separated bracket format `[1 2 3]`.
___
##### Run Command:

`$ wasmtk run arrays.ts`

##### Results:

`emp: [0 0 0 0 0]`
`set: [0 0 0 0 100]`
`get: 100`
`len: 5`
`dcl: [1 2 3 4 5]`
`2d: [[0 1 2] [1 2 3]]`

___

##### Run Command:

`$ wasmtk wasic arrays.ts`

`$ wasmtk run arrays.wasm`

##### Results:

`emp: [0 0 0 0 0]`
`set: [0 0 0 0 100]`
`get: 100`
`len: 5`
`dcl: [1 2 3 4 5]`
`2d: [[0 1 2] [1 2 3]]`

___

##### Run Command:

`$ wasmtk info arrays.wasm`
