#### wasic has no `Buffer` or `atob`/`btoa`. This lesson implements standard and URL-safe Base64 encoding and decoding using pure wasic-compatible arithmetic, producing the same output as Go's `encoding/base64`.
___
##### Run Command:

`$ wasmtk run base64-encoding.ts`

##### Results:

`YWJjMTIzIT8kKiYoKSctPUB+`
`abc123!?$*&()'-=@~`
``
`YWJjMTIzIT8kKiYoKSctPUB-`
`abc123!?$*&()'-=@~`

___

##### Run Command:

`$ wasmtk wasic base64-encoding.ts`

`$ wasmtk run base64-encoding.wasm`

##### Results:

`YWJjMTIzIT8kKiYoKSctPUB+`
`abc123!?$*&()'-=@~`
``
`YWJjMTIzIT8kKiYoKSctPUB-`
`abc123!?$*&()'-=@~`

___

##### Run Command:

`$ wasmtk info base64-encoding.wasm`
