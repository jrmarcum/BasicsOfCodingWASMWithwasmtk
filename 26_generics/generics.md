#### wasic does not support TypeScript generic type parameters. This lesson implements concrete typed versions: `slicesIndexStr` for string slices and a `NumNode`-based linked list for numbers, matching Go's generic examples.
___
##### Run Command:

`$ wasmtk run generics.ts`

##### Results:

`index of zoo: 2`
`list: [10 13 23]`

___

##### Run Command:

`$ wasmtk wasic generics.ts`

`$ wasmtk run generics.wasm`

##### Results:

`index of zoo: 2`
`list: [10 13 23]`

___

##### Run Command:

`$ wasmtk info generics.wasm`
