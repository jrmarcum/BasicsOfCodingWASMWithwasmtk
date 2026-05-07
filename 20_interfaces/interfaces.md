#### WebAssembly has no vtable-based interfaces. This lesson uses a tagged struct (`kind` discriminator) with explicit dispatch functions, matching Go's structural interface dispatch.
___
##### Run Command:

`$ wasmtk run interfaces.ts`

##### Results:

`{3 4}`
`12`
`14`
`{5}`
`78.53981633974483`
`31.41592653589793`

___

##### Run Command:

`$ wasmtk wasic interfaces.ts`

`$ wasmtk run interfaces.wasm`

##### Results:

`{3 4}`
`12`
`14`
`{5}`
`78.53981633974483`
`31.41592653589793`

___

##### Run Command:

`$ wasmtk info interfaces.wasm`
