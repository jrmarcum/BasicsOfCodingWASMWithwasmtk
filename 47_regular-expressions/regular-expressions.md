#### wasic TypeScript has no `RegExp` object. This lesson hard-codes the outputs that Go's `regexp` package produces for `p([a-z]+)ch` against the test strings, preserving the lesson for comparative study.
___
##### Run Command:

`$ wasmtk run regular-expressions.ts`

##### Results:

`true`
`true`
`peach`
`[0 5]`
`[peach each]`
`[0 5 1 4]`
`[peach punch pinch]`
`[[0 5 1 4] [6 11 7 10] [12 17 13 16]]`
`[peach punch]`
`true`
`p([a-z]+)ch`
`a <fruit>`
`a PEACH`

___

##### Run Command:

`$ wasmtk wasic regular-expressions.ts`

`$ wasmtk run regular-expressions.wasm`

##### Results:

`true`
`true`
`peach`
`[0 5]`
`[peach each]`
`[0 5 1 4]`
`[peach punch pinch]`
`[[0 5 1 4] [6 11 7 10] [12 17 13 16]]`
`[peach punch]`
`true`
`p([a-z]+)ch`
`a <fruit>`
`a PEACH`

___

##### Run Command:

`$ wasmtk info regular-expressions.wasm`
