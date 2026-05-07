#### WebAssembly has no `Date` API or time-formatting library. This lesson uses static Go playground reference values to show the same output as Go's `time.Format`, `time.Parse`, and layout patterns.
___
##### Run Command:

`$ wasmtk run time-formatting-parsing.ts`

##### Results:

`2009-11-10T23:00:00.000Z`
`2012-11-01T22:08:41.000Z`
`11:00PM`
`Tue Nov 10 23:00:00 2009`
`2009-11-10T23:00:00.000Z`
`0000-01-01T20:41:00.000Z`
`2009-11-10T23:00:00-00:00`
`null`

___

##### Run Command:

`$ wasmtk wasic time-formatting-parsing.ts`

`$ wasmtk run time-formatting-parsing.wasm`

##### Results:

`2009-11-10T23:00:00.000Z`
`2012-11-01T22:08:41.000Z`
`11:00PM`
`Tue Nov 10 23:00:00 2009`
`2009-11-10T23:00:00.000Z`
`0000-01-01T20:41:00.000Z`
`2009-11-10T23:00:00-00:00`
`null`

___

##### Run Command:

`$ wasmtk info time-formatting-parsing.wasm`
