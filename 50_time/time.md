#### WebAssembly has no `Date` API. This lesson uses static reference-time values (Go playground time `2009-11-10` and the fixed `then` timestamp) to show the same fields that Go's `time` package outputs; duration values are approximate.
___
##### Run Command:

`$ wasmtk run time.ts`

##### Results:

`2009-11-10T23:00:00.000Z`
`2009-11-17T20:34:58.651Z`
`2009`
`November`
`17`
`20`
`34`
`58`
`651000000`
`UTC`
`Tuesday`
`true`
`false`
`false`
`145992.43... h`
`8759546.0... m`
`525572763.3... s`
`525572763349000000 ns`
`2026-05-04T20:34:58.651Z`
`1993-06-01T20:34:58.651Z`

___

##### Run Command:

`$ wasmtk wasic time.ts`

`$ wasmtk run time.wasm`

##### Results:

`2009-11-10T23:00:00.000Z`
`2009-11-17T20:34:58.651Z`
`2009`
`November`
`17`
`20`
`34`
`58`
`651000000`
`UTC`
`Tuesday`
`true`
`false`
`false`
`145992.43... h`
`8759546.0... m`
`525572763.3... s`
`525572763349000000 ns`
`2026-05-04T20:34:58.651Z`
`1993-06-01T20:34:58.651Z`

___

##### Run Command:

`$ wasmtk info time.wasm`
