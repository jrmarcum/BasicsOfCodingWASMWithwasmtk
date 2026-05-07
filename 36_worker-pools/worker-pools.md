#### WebAssembly has no goroutine worker pools. Jobs are dispatched sequentially in a round-robin fashion across 3 workers, showing the same start/finish pattern as the Go concurrent pool.
___
##### Run Command:

`$ wasmtk run worker-pools.ts`

##### Results:

`worker 1 started  job 1`
`worker 1 finished job 1`
`worker 2 started  job 2`
`worker 2 finished job 2`
`worker 3 started  job 3`
`worker 3 finished job 3`
`worker 1 started  job 4`
`worker 1 finished job 4`
`worker 2 started  job 5`
`worker 2 finished job 5`

___

##### Run Command:

`$ wasmtk wasic worker-pools.ts`

`$ wasmtk run worker-pools.wasm`

##### Results:

`worker 1 started  job 1`
`worker 1 finished job 1`
`worker 2 started  job 2`
`worker 2 finished job 2`
`worker 3 started  job 3`
`worker 3 finished job 3`
`worker 1 started  job 4`
`worker 1 finished job 4`
`worker 2 started  job 5`
`worker 2 finished job 5`

___

##### Run Command:

`$ wasmtk info worker-pools.wasm`
