#### WASI process argument access is not available through the wasic TypeScript API; this lesson demonstrates the expected output for the `foo` subcommand with `-enable -name=joe a1 a2`.
___
##### Run Command:

`$ wasmtk run command-line-subcommands.ts`

##### Results:

`subcommand 'foo'`
`  enable: true`
`  name: joe`
`  tail: [a1 a2]`

___

##### Run Command:

`$ wasmtk wasic command-line-subcommands.ts`

`$ wasmtk run command-line-subcommands.wasm`

##### Results:

`subcommand 'foo'`
`  enable: true`
`  name: joe`
`  tail: [a1 a2]`

___

##### Run Command:

`$ wasmtk info command-line-subcommands.wasm`
