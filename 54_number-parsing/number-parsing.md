#### wasic may not support `parseInt`/`parseFloat` (not in the documented subset). This lesson implements them manually as pure wasic-compatible functions.
___
##### Run Command:

`$ wasmtk run number-parsing.ts`

##### Results:

`1.234`
`123`
`456`
`789`
`135 <nil>`
`strconv.Atoi: parsing "wat": invalid syntax`

___

##### Run Command:

`$ wasmtk wasic number-parsing.ts`

`$ wasmtk run number-parsing.wasm`

##### Results:

`1.234`
`123`
`456`
`789`
`135 <nil>`
`strconv.Atoi: parsing "wat": invalid syntax`

___

##### Run Command:

`$ wasmtk info number-parsing.wasm`
