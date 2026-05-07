#### WebAssembly has no native hash-map type. This lesson implements a map with parallel key/value arrays and sorted output to match Go's alphabetical map printing.
___
##### Run Command:

`$ wasmtk run maps.ts`

##### Results:

`map: map[k1:7 k2:13]`
`v1: 7`
`v3: 0`
`len: 2`
`map: map[k1:7]`
`prs: false`
`map: map[bar:2 foo:1]`

___

##### Run Command:

`$ wasmtk wasic maps.ts`

`$ wasmtk run maps.wasm`

##### Results:

`map: map[k1:7 k2:13]`
`v1: 7`
`v3: 0`
`len: 2`
`map: map[k1:7]`
`prs: false`
`map: map[bar:2 foo:1]`

___

##### Run Command:

`$ wasmtk info maps.wasm`
