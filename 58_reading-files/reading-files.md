#### WASI file I/O is not available through the wasic TypeScript API; this lesson simulates reading `tmp/dat.txt` (containing `hello\ngo\n`) with hardcoded values.
___
##### Run Command:

`$ wasmtk run reading-files.ts`

##### Results:

`hello`
`go`
`5 bytes: hello`
`2 bytes @ 6: go`
`2 bytes @ 6: go`
`5 bytes: hello`

___

##### Run Command:

`$ wasmtk wasic reading-files.ts`

`$ wasmtk run reading-files.wasm`

##### Results:

`hello`
`go`
`5 bytes: hello`
`2 bytes @ 6: go`
`2 bytes @ 6: go`
`5 bytes: hello`

___

##### Run Command:

`$ wasmtk info reading-files.wasm`
