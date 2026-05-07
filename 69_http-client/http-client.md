#### HTTP networking is not available in WASI; this lesson demonstrates the expected output for an HTTP GET request to a remote server.
___
##### Run Command:

`$ wasmtk run http-client.ts`

##### Results:

`Response status: 200 OK`
`<!DOCTYPE html>`
`<html>`
`  <head>`
`    <meta charset="utf-8">`
`    <title>Go by Example</title>`

___

##### Run Command:

`$ wasmtk wasic http-client.ts`

`$ wasmtk run http-client.wasm`

##### Results:

`Response status: 200 OK`
`<!DOCTYPE html>`
`<html>`
`  <head>`
`    <meta charset="utf-8">`
`    <title>Go by Example</title>`

___

##### Run Command:

`$ wasmtk info http-client.wasm`
