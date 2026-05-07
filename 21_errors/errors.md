#### WebAssembly uses struct-based error returns (a `Result` interface with a `hasErr` discriminator) instead of Go's multiple-return error idiom. Custom error types are plain interfaces; type assertion is replaced by the `hasErr` flag.
___
##### Run Command:

`$ wasmtk run errors.ts`

##### Results:

`f1 worked: 10`
`f1 failed: can't work with 42`
`f2 worked: 10`
`f2 failed: 42 - can't work with 42`
`42`
`can't work with 42`

___

##### Run Command:

`$ wasmtk wasic errors.ts`

`$ wasmtk run errors.wasm`

##### Results:

`f1 worked: 10`
`f1 failed: can't work with 42`
`f2 worked: 10`
`f2 failed: 42 - can't work with 42`
`42`
`can't work with 42`

___

##### Run Command:

`$ wasmtk info errors.wasm`
