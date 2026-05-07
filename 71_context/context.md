#### HTTP context and request cancellation are not available in WASI; this lesson demonstrates the expected output for a request that completes normally before cancellation.
___
##### Run Command:

`$ wasmtk run context.ts`

##### Results:

`server: hello handler started`
`server: hello handler ended`

___

##### Run Command:

`$ wasmtk wasic context.ts`

`$ wasmtk run context.wasm`

##### Results:

`server: hello handler started`
`server: hello handler ended`

___

##### Run Command:

`$ wasmtk info context.wasm`
