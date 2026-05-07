#### WebAssembly has no timers or async primitives. This lesson simulates Go's `time.After` timeout pattern with a synchronous helper that compares durations: the first operation exceeds its 100 ms budget, the second completes within 300 ms.
___
##### Run Command:

`$ wasmtk run timeouts.ts`

##### Results:

`timeout 1`
`result 2`

___

##### Run Command:

`$ wasmtk wasic timeouts.ts`

`$ wasmtk run timeouts.wasm`

##### Results:

`timeout 1`
`result 2`

___

##### Run Command:

`$ wasmtk info timeouts.wasm`
