#### WebAssembly has no timer primitives. This lesson produces the same output as the Go timer example: Timer 1 fires after its delay, and Timer 2 is stopped before firing.
___
##### Run Command:

`$ wasmtk run timers.ts`

##### Results:

`Timer 1 fired`
`Timer 2 stopped`

___

##### Run Command:

`$ wasmtk wasic timers.ts`

`$ wasmtk run timers.wasm`

##### Results:

`Timer 1 fired`
`Timer 2 stopped`

___

##### Run Command:

`$ wasmtk info timers.wasm`
