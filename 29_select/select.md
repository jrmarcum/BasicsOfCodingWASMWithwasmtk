#### WebAssembly has no `select` or concurrent channel sends. This lesson produces the same two-line output by calling two functions sequentially, matching the deterministic result that Go's `select` reaches when both channels resolve.
___
##### Run Command:

`$ wasmtk run select.ts`

##### Results:

`received one`
`received two`

___

##### Run Command:

`$ wasmtk wasic select.ts`

`$ wasmtk run select.wasm`

##### Results:

`received one`
`received two`

___

##### Run Command:

`$ wasmtk info select.wasm`
