#### WASI directory operations are not available through the wasic TypeScript API; this lesson prints the expected directory listing output.
___
##### Run Command:

`$ wasmtk run directories.ts`

##### Results:

`Listing subdir/parent`
`  child true`
`  file2 false`
`  file3 false`
`Listing subdir/parent/child`
`  file4 false`
`Visiting subdir`
`  subdir true`
`  subdir/file1 false`
`  subdir/parent true`
`  subdir/parent/child true`
`  subdir/parent/child/file4 false`
`  subdir/parent/file2 false`
`  subdir/parent/file3 false`

___

##### Run Command:

`$ wasmtk wasic directories.ts`

`$ wasmtk run directories.wasm`

##### Results:

`Listing subdir/parent`
`  child true`
`  file2 false`
`  file3 false`
`Listing subdir/parent/child`
`  file4 false`
`Visiting subdir`
`  subdir true`
`  subdir/file1 false`
`  subdir/parent true`
`  subdir/parent/child true`
`  subdir/parent/child/file4 false`
`  subdir/parent/file2 false`
`  subdir/parent/file3 false`

___

##### Run Command:

`$ wasmtk info directories.wasm`
