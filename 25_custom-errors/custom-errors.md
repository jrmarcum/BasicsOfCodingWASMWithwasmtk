#### Go's custom error types are implemented as plain interfaces; `errors.As` type-checking is replaced by the `hasErr` discriminator field.
___
##### Run Command:

`$ wasmtk run custom-errors.ts`

##### Results:

`42`
`can't work with it`

___

##### Run Command:

`$ wasmtk wasic custom-errors.ts`

`$ wasmtk run custom-errors.wasm`

##### Results:

`42`
`can't work with it`

___

##### Run Command:

`$ wasmtk info custom-errors.wasm`
