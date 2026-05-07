#### WebAssembly uses interface-defined structs laid out in linear memory. Factory functions replace Go's struct literal constructors. The `&` prefix for pointer-to-struct in Go's `&{Ann 42}` does not exist — all struct variables are references in wasic.
___
##### Run Command:

`$ wasmtk run structs.ts`

##### Results:

`{Bob 20}`
`{Alice 30}`
`{Fred 0}`
`{Ann 42}`
`{Jon 42}`
`Sean`
`50`
`51`
`{Rex true}`

___

##### Run Command:

`$ wasmtk wasic structs.ts`

`$ wasmtk run structs.wasm`

##### Results:

`{Bob 20}`
`{Alice 30}`
`{Fred 0}`
`{Ann 42}`
`{Jon 42}`
`Sean`
`50`
`51`
`{Rex true}`

___

##### Run Command:

`$ wasmtk info structs.wasm`
