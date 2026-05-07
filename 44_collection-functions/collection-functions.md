#### wasic TypeScript array methods (`forEach`, `filter`, `map`) are available, but this lesson implements them explicitly to show Go's manual-helper pattern. Output matches Go's `[peach pear plum]` format.
___
##### Run Command:

`$ wasmtk run collection-functions.ts`

##### Results:

`2`
`false`
`true`
`false`
`[peach pear plum]`
`[PEACH APPLE PEAR PLUM]`

___

##### Run Command:

`$ wasmtk wasic collection-functions.ts`

`$ wasmtk run collection-functions.wasm`

##### Results:

`2`
`false`
`true`
`false`
`[peach pear plum]`
`[PEACH APPLE PEAR PLUM]`

___

##### Run Command:

`$ wasmtk info collection-functions.wasm`
