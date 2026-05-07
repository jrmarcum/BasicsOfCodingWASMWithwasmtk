#### Go's `range` over maps and strings is replaced with indexed loops over parallel arrays. String character code points are inlined constants (`g`=103, `o`=111) since wasic has no `codePointAt` method.
___
##### Run Command:

`$ wasmtk run range.ts`

##### Results:

`sum: 6`
`index: 1`
`a -> apple`
`b -> banana`
`key: a`
`key: b`
`0 103`
`1 111`

___

##### Run Command:

`$ wasmtk wasic range.ts`

`$ wasmtk run range.wasm`

##### Results:

`sum: 6`
`index: 1`
`a -> apple`
`b -> banana`
`key: a`
`key: b`
`0 103`
`1 111`

___

##### Run Command:

`$ wasmtk info range.wasm`
