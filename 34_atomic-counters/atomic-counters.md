#### WebAssembly is single-threaded so ordinary `++` is already atomic — no `sync/atomic` equivalent is needed. This lesson runs the same 50 × 1000 increment pattern sequentially.
___
##### Run Command:

`$ wasmtk run atomic-counters.ts`

##### Results:

`ops: 50000`

___

##### Run Command:

`$ wasmtk wasic atomic-counters.ts`

`$ wasmtk run atomic-counters.wasm`

##### Results:

`ops: 50000`

___

##### Run Command:

`$ wasmtk info atomic-counters.wasm`
