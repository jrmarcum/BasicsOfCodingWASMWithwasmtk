#### wasic has no crypto API. The SHA1 hash of `"sha1 this string"` is pre-computed (`cf23df...`); the output is identical to Go's `crypto/sha1`.
___
##### Run Command:

`$ wasmtk run sha1-hashes.ts`

##### Results:

`sha1 this string`
`cf23df2207d99a74fbe169e3eba035e633b65d94`

___

##### Run Command:

`$ wasmtk wasic sha1-hashes.ts`

`$ wasmtk run sha1-hashes.wasm`

##### Results:

`sha1 this string`
`cf23df2207d99a74fbe169e3eba035e633b65d94`

___

##### Run Command:

`$ wasmtk info sha1-hashes.wasm`
