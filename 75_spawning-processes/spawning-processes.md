#### Spawning external processes via `exec.Command` is not available in WASI; in Go, this would run `date`, `grep`, and `ls -a -l -h` as child processes.
___
##### Run Command:

`$ wasmtk run spawning-processes.ts`

##### Results:

`Spawning processes is not available in WASI`

___

##### Run Command:

`$ wasmtk wasic spawning-processes.ts`

`$ wasmtk run spawning-processes.wasm`

##### Results:

`Spawning processes is not available in WASI`

___

##### Run Command:

`$ wasmtk info spawning-processes.wasm`
