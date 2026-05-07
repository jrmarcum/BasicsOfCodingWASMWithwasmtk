#### WebAssembly functions return a single value; multiple return values are packed into a struct (interface). Destructuring uses field access instead of Go's tuple or blank identifier.
___
##### Run Command:

`$ wasmtk run multiple-return-values.ts`

##### Results:

`3`
`7`
`7`

___

##### Run Command:

`$ wasmtk wasic multiple-return-values.ts`

`$ wasmtk run multiple-return-values.wasm`

##### Results:

`3`
`7`
`7`

___

##### Run Command:

`$ wasmtk info multiple-return-values.wasm`
