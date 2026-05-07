#### WebAssembly has no pointers. Primitive values pass by copy; structs (interfaces) pass by reference in linear memory. This lesson demonstrates the equivalent: `zeroval` copies the number (no effect), `zeroref` mutates the struct field. No memory address is printed.
___
##### Run Command:

`$ wasmtk run pointers.ts`

##### Results:

`initial: 1`
`zeroval: 1`
`zeroref: 0`
`reference: {val:0}`

___

##### Run Command:

`$ wasmtk wasic pointers.ts`

`$ wasmtk run pointers.wasm`

##### Results:

`initial: 1`
`zeroval: 1`
`zeroref: 0`
`reference: {val:0}`

___

##### Run Command:

`$ wasmtk info pointers.wasm`
