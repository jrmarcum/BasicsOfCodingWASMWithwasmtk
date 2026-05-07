#### OS signal handling is not available in WASI; this lesson demonstrates the expected output for a program that receives `SIGINT` (`Ctrl-C`).
___
##### Run Command:

`$ wasmtk run signals.ts`

##### Results:

`awaiting signal`
`^C`
`interrupt signal received`
`exiting`

___

##### Run Command:

`$ wasmtk wasic signals.ts`

`$ wasmtk run signals.wasm`

##### Results:

`awaiting signal`
`^C`
`interrupt signal received`
`exiting`

___

##### Run Command:

`$ wasmtk info signals.wasm`
