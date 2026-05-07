#### WebAssembly has no `Date` API. This lesson uses the Go playground epoch (`2009-11-10T23:00:00 UTC`, Unix seconds `1257894000`) as static values to illustrate `time.Unix`, `time.UnixMilli`, and `time.UnixNano`.
___
##### Run Command:

`$ wasmtk run epoch.ts`

##### Results:

`2009-11-10T23:00:00.000Z`
`1257894000`
`1257894000000`
`1257894000000000000`
`2009-11-10T23:00:00.000Z`
`2009-11-10T23:00:00.000Z`

___

##### Run Command:

`$ wasmtk wasic epoch.ts`

`$ wasmtk run epoch.wasm`

##### Results:

`2009-11-10T23:00:00.000Z`
`1257894000`
`1257894000000`
`1257894000000000000`
`2009-11-10T23:00:00.000Z`
`2009-11-10T23:00:00.000Z`

___

##### Run Command:

`$ wasmtk info epoch.wasm`
