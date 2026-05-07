#### In wasic TypeScript the process exit code cannot be set; `throw` exits immediately bypassing deferred calls, mirroring Go's `os.Exit`. In Go, `go run` reports `exit status 3`; the `!` from `defer` never prints.
___
##### Run Command:

`$ wasmtk run exit.ts`

##### Results:

`exit status 3`

___

##### Run Command:

`$ wasmtk wasic exit.ts`

`$ wasmtk run exit.wasm`

##### Results:

`exit status 3`

___

##### Run Command:

`$ wasmtk info exit.wasm`
