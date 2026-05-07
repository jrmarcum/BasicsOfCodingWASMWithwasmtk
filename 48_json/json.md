#### wasic TypeScript has no `JSON.parse`/`JSON.stringify`. This lesson manually builds JSON strings and shows the same parsed output as Go's `encoding/json`, preserving the lesson structure for comparative study.
___
##### Run Command:

`$ wasmtk run json.ts`

##### Results:

`true`
`1`
`2.34`
`"vector"`
`["apple","peach","pear"]`
`{"apple":5,"lettuce":7}`
`{"Page":1,"Fruits":["apple","peach","pear"]}`
`{"page":1,"fruits":["apple","peach","pear"]}`
`{num: 6.13, strs: [a b]}`
`6.13`
`a`
`{1 [apple peach]}`
`apple`
`{"apple":5,"lettuce":7}`

___

##### Run Command:

`$ wasmtk wasic json.ts`

`$ wasmtk run json.wasm`

##### Results:

`true`
`1`
`2.34`
`"vector"`
`["apple","peach","pear"]`
`{"apple":5,"lettuce":7}`
`{"Page":1,"Fruits":["apple","peach","pear"]}`
`{"page":1,"fruits":["apple","peach","pear"]}`
`{num: 6.13, strs: [a b]}`
`6.13`
`a`
`{1 [apple peach]}`
`apple`
`{"apple":5,"lettuce":7}`

___

##### Run Command:

`$ wasmtk info json.wasm`
