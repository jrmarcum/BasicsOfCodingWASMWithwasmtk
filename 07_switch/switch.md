#### WebAssembly has no `Date` API; day-of-week and hour use static values (day 2 = Tuesday, hour 15 = 3 PM). Type inspection uses a string tag instead of Go's interface type-switch.
___
##### Run Command:

`$ wasmtk run switch.ts`

##### Results:

`write 2 as two`
`It's a weekday`
`It's after noon`
`bool`
`int`
`unknown type string`

___

##### Run Command:

`$ wasmtk wasic switch.ts`

`$ wasmtk run switch.wasm`

##### Results:

`write 2 as two`
`It's a weekday`
`It's after noon`
`bool`
`int`
`unknown type string`

___

##### Run Command:

`$ wasmtk info switch.wasm`
