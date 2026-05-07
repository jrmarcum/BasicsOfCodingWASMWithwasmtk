#### Replacing the current process via `syscall.Exec` is not available in WASI; in Go, this would exec `ls -a -l -h` and replace the running process.
___
##### Run Command:

`$ wasmtk run execing-processes.ts`

##### Results:

`syscall.Exec is not available in WASI`

___

##### Run Command:

`$ wasmtk wasic execing-processes.ts`

`$ wasmtk run execing-processes.wasm`

##### Results:

`syscall.Exec is not available in WASI`

___

##### Run Command:

`$ wasmtk info execing-processes.wasm`
