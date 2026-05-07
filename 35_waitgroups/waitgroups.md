#### WebAssembly has no goroutines or `sync.WaitGroup`. Workers run sequentially rather than concurrently, so each worker's "starting" and "done" messages appear together. The Go output interleaves all starts before all dones; the wasic output prints each worker's full cycle in order.
___
##### Run Command:

`$ wasmtk run waitgroups.ts`

##### Results:

`Worker 1 starting`
`Worker 1 done`
`Worker 2 starting`
`Worker 2 done`
`Worker 3 starting`
`Worker 3 done`
`Worker 4 starting`
`Worker 4 done`
`Worker 5 starting`
`Worker 5 done`

___

##### Run Command:

`$ wasmtk wasic waitgroups.ts`

`$ wasmtk run waitgroups.wasm`

##### Results:

`Worker 1 starting`
`Worker 1 done`
`Worker 2 starting`
`Worker 2 done`
`Worker 3 starting`
`Worker 3 done`
`Worker 4 starting`
`Worker 4 done`
`Worker 5 starting`
`Worker 5 done`

___

##### Run Command:

`$ wasmtk info waitgroups.wasm`
