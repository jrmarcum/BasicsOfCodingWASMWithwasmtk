#### WebAssembly uses IEEE 754 f64 arithmetic; `3e20 / 500000000` yields `600000000000` in decimal notation (Go's `fmt.Println` uses scientific notation `6e+11`).
___
##### Run Command:

`$ wasmtk run constants.ts`

##### Results:

`constant`
`600000000000`
`600000000000`
`-0.28470407323754404`

___

##### Run Command:

`$ wasmtk wasic constants.ts`

`$ wasmtk run constants.wasm`

##### Results:

`constant`
`600000000000`
`600000000000`
`-0.28470407323754404`

___

##### Run Command:

`$ wasmtk info constants.wasm`
