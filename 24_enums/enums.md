#### Go's `iota`-based enums map directly to wasic's numeric `enum` keyword; enum members become `i32` constants in the compiled WASM.
___
##### Run Command:

`$ wasmtk run enums.ts`

##### Results:

`connected`
`idle`

___

##### Run Command:

`$ wasmtk wasic enums.ts`

`$ wasmtk run enums.wasm`

##### Results:

`connected`
`idle`

___

##### Run Command:

`$ wasmtk info enums.wasm`
