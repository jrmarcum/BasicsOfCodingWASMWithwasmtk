#### WASI process argument access is not available through the wasic TypeScript API; this lesson demonstrates the expected output for running with arguments `a b c d`.
___
##### Run Command:

`$ wasmtk run command-line-arguments.ts`

##### Results:

`[./command-line-arguments a b c d]`
`[a b c d]`
`c`

___

##### Run Command:

`$ wasmtk wasic command-line-arguments.ts`

`$ wasmtk run command-line-arguments.wasm`

##### Results:

`[./command-line-arguments a b c d]`
`[a b c d]`
`c`

___

##### Run Command:

`$ wasmtk info command-line-arguments.wasm`
