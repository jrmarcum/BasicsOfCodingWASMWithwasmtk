#### WebAssembly is single-threaded; goroutines are implemented as sequential function calls. Output order is deterministic — identical to the Go output produced when the goroutine completes before `done` prints.
___
##### Run Command:

`$ wasmtk run goroutines.ts`

##### Results:

`direct : 0`
`direct : 1`
`direct : 2`
`goroutine : 0`
`goroutine : 1`
`goroutine : 2`
`going`
`done`

___

##### Run Command:

`$ wasmtk wasic goroutines.ts`

`$ wasmtk run goroutines.wasm`

##### Results:

`direct : 0`
`direct : 1`
`direct : 2`
`goroutine : 0`
`goroutine : 1`
`goroutine : 2`
`going`
`done`

___

##### Run Command:

`$ wasmtk info goroutines.wasm`
