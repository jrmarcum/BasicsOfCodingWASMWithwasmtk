#### Go's `panic` maps to `throw new Error(...)` in wasic TypeScript. The program prints `5`, then throws an unhandled error and exits with a non-zero code. Stack trace details vary with environment.
___
##### Run Command:

`$ wasmtk run panic.ts`

##### Results:

`5`
`error: expected positive, got -1`

___

##### Run Command:

`$ wasmtk wasic panic.ts`

`$ wasmtk run panic.wasm`

##### Results:

`5`
`error: expected positive, got -1`

___

##### Run Command:

`$ wasmtk info panic.wasm`
