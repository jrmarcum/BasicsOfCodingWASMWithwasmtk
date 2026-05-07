#### WASI command-line flag parsing is not available through the wasic TypeScript API; this lesson demonstrates the expected output for flags `-word=opt -numb=7 -fork -svar=flag`.
___
##### Run Command:

`$ wasmtk run command-line-flags.ts`

##### Results:

`word: opt`
`numb: 7`
`fork: true`
`svar: flag`
`tail: []`

___

##### Run Command:

`$ wasmtk wasic command-line-flags.ts`

`$ wasmtk run command-line-flags.wasm`

##### Results:

`word: opt`
`numb: 7`
`fork: true`
`svar: flag`
`tail: []`

___

##### Run Command:

`$ wasmtk info command-line-flags.wasm`
