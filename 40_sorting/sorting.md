#### wasic has no built-in sort; this lesson implements bubble sort for strings and numbers. Output uses Go's space-separated bracket notation `[a b c]`.
___
##### Run Command:

`$ wasmtk run sorting.ts`

##### Results:

`Strings: [a b c]`
`Ints:    [2 4 7]`
`Sorted:  true`

___

##### Run Command:

`$ wasmtk wasic sorting.ts`

`$ wasmtk run sorting.wasm`

##### Results:

`Strings: [a b c]`
`Ints:    [2 4 7]`
`Sorted:  true`

___

##### Run Command:

`$ wasmtk info sorting.wasm`
