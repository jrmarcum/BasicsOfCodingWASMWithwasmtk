#### WebAssembly has no method syntax; methods are plain functions that take a struct (interface) as their first parameter. There is no distinction between pointer and value receivers — struct parameters are always passed as memory pointers in wasic.
___
##### Run Command:

`$ wasmtk run methods.ts`

##### Results:

`area: 50`
`perim: 30`

___

##### Run Command:

`$ wasmtk wasic methods.ts`

`$ wasmtk run methods.wasm`

##### Results:

`area: 50`
`perim: 30`

___

##### Run Command:

`$ wasmtk info methods.wasm`
