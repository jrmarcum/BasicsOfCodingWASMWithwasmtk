#### WASI environment variable access is not available through the wasic TypeScript API; this lesson demonstrates the expected output format. The full environment key list varies by machine.
___
##### Run Command:

`$ wasmtk run environment-variables.ts`

##### Results:

`FOO: 1`
`BAR: `

___

##### Run Command:

`$ wasmtk wasic environment-variables.ts`

`$ wasmtk run environment-variables.wasm`

##### Results:

`FOO: 1`
`BAR: `

___

##### Run Command:

`$ wasmtk info environment-variables.wasm`
