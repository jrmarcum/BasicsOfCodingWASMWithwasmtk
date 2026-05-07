#### WASI file I/O is not available through the wasic TypeScript API; this lesson prints the byte counts that would have been written to the files.
___
##### Run Command:

`$ wasmtk run writing-files.ts`

##### Results:

`wrote 5 bytes`
`wrote 7 bytes`
`wrote 9 bytes`

___

##### Run Command:

`$ wasmtk wasic writing-files.ts`

`$ wasmtk run writing-files.wasm`

##### Results:

`wrote 5 bytes`
`wrote 7 bytes`
`wrote 9 bytes`

___

##### Run Command:

`$ wasmtk info writing-files.wasm`
