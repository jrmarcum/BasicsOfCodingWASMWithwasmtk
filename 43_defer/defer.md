#### JavaScript has no built-in `defer`; this lesson simulates Go's defer using a LIFO function array. In production wasic code, `try/finally` is the idiomatic cleanup pattern.
___
##### Run Command:

`$ wasmtk run defer.ts`

##### Results:

`counting`
`done`
`4`
`3`
`2`
`1`
`0`

___

##### Run Command:

`$ wasmtk wasic defer.ts`

`$ wasmtk run defer.wasm`

##### Results:

`counting`
`done`
`4`
`3`
`2`
`1`
`0`

___

##### Run Command:

`$ wasmtk info defer.wasm`
