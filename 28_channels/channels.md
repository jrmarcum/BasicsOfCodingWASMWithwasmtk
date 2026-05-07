#### WebAssembly has no channels or async primitives. This lesson simulates a channel with a shared variable: `send` writes to it and `receive` reads from it, producing the same `ping` output as the Go channel example.
___
##### Run Command:

`$ wasmtk run channels.ts`

##### Results:

`ping`

___

##### Run Command:

`$ wasmtk wasic channels.ts`

`$ wasmtk run channels.wasm`

##### Results:

`ping`

___

##### Run Command:

`$ wasmtk info channels.wasm`
