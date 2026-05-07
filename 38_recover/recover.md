#### Go's `defer`+`recover()` maps to a `try/catch` block in wasic TypeScript; `throw new Error(...)` replaces `panic(...)`.
___
##### Run Command:

`$ wasmtk run recover.ts`

##### Results:

`Recovered. Error:`
` a problem`

___

##### Run Command:

`$ wasmtk wasic recover.ts`

`$ wasmtk run recover.wasm`

##### Results:

`Recovered. Error:`
` a problem`

___

##### Run Command:

`$ wasmtk info recover.wasm`
