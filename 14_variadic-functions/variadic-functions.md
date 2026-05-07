##### Run Command:

`$ wasmtk run variadic-functions.ts`

##### Results:

`[1 2] 3`
`[1 2 3] 6`
`[1 2 3 4] 10`

___

##### Run Command:

`$ wasmtk wasic variadic-functions.ts`

`$ wasmtk run variadic-functions.wasm`

##### Results:

`[1 2] 3`
`[1 2 3] 6`
`[1 2 3 4] 10`

___

##### Run Command:

`$ wasmtk info variadic-functions.wasm`
