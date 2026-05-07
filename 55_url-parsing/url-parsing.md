#### wasic has no `URL` API. This lesson parses a URL with manual string operations, producing the same output as Go's `url.Parse`. Query parameters use Go's `map[k:[v]]` format.
___
##### Run Command:

`$ wasmtk run url-parsing.ts`

##### Results:

`postgres`
`user:pass`
`user`
`pass`
`host.com:5432`
`host.com`
`5432`
`/path`
`f`
`k=v`
`map[k:[v]]`
`v`

___

##### Run Command:

`$ wasmtk wasic url-parsing.ts`

`$ wasmtk run url-parsing.wasm`

##### Results:

`postgres`
`user:pass`
`user`
`pass`
`host.com:5432`
`host.com`
`5432`
`/path`
`f`
`k=v`
`map[k:[v]]`
`v`

___

##### Run Command:

`$ wasmtk info url-parsing.wasm`
