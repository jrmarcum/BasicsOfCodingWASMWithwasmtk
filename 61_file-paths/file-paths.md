##### Run Command:

`$ wasmtk run file-paths.ts`

##### Results:

`p: dir1/dir2/filename`
`dir1/filename`
`dir1/filename`
`Dir(p): dir1/dir2`
`Base(p): filename`
`false`
`true`
`.json`
`config`
`t/file`
`../c/t/file`

___

##### Run Command:

`$ wasmtk wasic file-paths.ts`

`$ wasmtk run file-paths.wasm`

##### Results:

`p: dir1/dir2/filename`
`dir1/filename`
`dir1/filename`
`Dir(p): dir1/dir2`
`Base(p): filename`
`false`
`true`
`.json`
`config`
`t/file`
`../c/t/file`

___

##### Run Command:

`$ wasmtk info file-paths.wasm`
