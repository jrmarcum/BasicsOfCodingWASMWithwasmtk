#### wasic TypeScript has no crypto API; the SHA256 hash of `"sha256 this string"` is pre-computed and hard-coded.
___
##### Run Command:

`$ wasmtk run sha256-hashes.ts`

##### Results:

`sha256 this string`
`1af1dfa857bf1d8814fe1af8983c18080019922e557f15a8a0d3db739d77aacb`

___

##### Run Command:

`$ wasmtk wasic sha256-hashes.ts`

`$ wasmtk run sha256-hashes.wasm`

##### Results:

`sha256 this string`
`1af1dfa857bf1d8814fe1af8983c18080019922e557f15a8a0d3db739d77aacb`

___

##### Run Command:

`$ wasmtk info sha256-hashes.wasm`
