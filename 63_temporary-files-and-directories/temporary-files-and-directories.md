#### WASI temporary file creation is not available through the wasic TypeScript API; this lesson prints example path names to demonstrate the expected output format. Actual paths vary with each run.
___
##### Run Command:

`$ wasmtk run temporary-files-and-directories.ts`

##### Results:

`Temp file name: /tmp/sample123456789`
`Temp dir name: /tmp/sampledir987654321`

___

##### Run Command:

`$ wasmtk wasic temporary-files-and-directories.ts`

`$ wasmtk run temporary-files-and-directories.wasm`

##### Results:

`Temp file name: /tmp/sample123456789`
`Temp dir name: /tmp/sampledir987654321`

___

##### Run Command:

`$ wasmtk info temporary-files-and-directories.wasm`
