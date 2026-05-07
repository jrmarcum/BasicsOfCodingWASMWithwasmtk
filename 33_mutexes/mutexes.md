#### WebAssembly is single-threaded so no mutex is needed — sequential increments are already safe. This lesson demonstrates the Go mutex pattern by sequentially calling three workers, producing the same counter totals as the Go concurrent example.
___
##### Run Command:

`$ wasmtk run mutexes.ts`

##### Results:

`map[a:20000 b:10000]`

___

##### Run Command:

`$ wasmtk wasic mutexes.ts`

`$ wasmtk run mutexes.wasm`

##### Results:

`map[a:20000 b:10000]`

___

##### Run Command:

`$ wasmtk info mutexes.wasm`
