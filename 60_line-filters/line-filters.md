#### WASI stdin reading is not available; this lesson demonstrates uppercasing with hardcoded input. In Go the output comes from piping `tmp/lines.txt` through the filter program.
___
##### Run Command:

`$ wasmtk run line-filters.ts`

##### Results:

`HELLO`
`FILTER`

___

##### Run Command:

`$ wasmtk wasic line-filters.ts`

`$ wasmtk run line-filters.wasm`

##### Results:

`HELLO`
`FILTER`

___

##### Run Command:

`$ wasmtk info line-filters.wasm`
