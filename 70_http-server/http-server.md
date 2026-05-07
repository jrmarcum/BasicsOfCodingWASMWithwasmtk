#### HTTP servers are not available in WASI; this lesson demonstrates the handler functions used to serve `/hello` and `/headers` routes.
___
##### Run Command:

`$ wasmtk run http-server.ts`

##### Results:

`hello`

___

##### Run Command:

`$ wasmtk wasic http-server.ts`

`$ wasmtk run http-server.wasm`

##### Results:

`hello`

___

##### Run Command:

`$ wasmtk info http-server.wasm`
