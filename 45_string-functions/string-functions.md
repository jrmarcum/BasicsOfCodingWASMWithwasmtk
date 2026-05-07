#### Go's `strings` package functions are implemented manually in wasic TypeScript. String methods `indexOf`, `slice`, `toLowerCase`, and `toUpperCase` are available natively.
___
##### Run Command:

`$ wasmtk run string-functions.ts`

##### Results:

`Contains:   true`
`Count:      2`
`HasPrefix:  true`
`HasSuffix:  true`
`Index:      1`
`Join:       a-b`
`Repeat:     aaaaa`
`Replace:    f00`
`Replace:    f0o`
`Split:      [a b c d e]`
`ToLower:    test`
`ToUpper:    TEST`

___

##### Run Command:

`$ wasmtk wasic string-functions.ts`

`$ wasmtk run string-functions.wasm`

##### Results:

`Contains:   true`
`Count:      2`
`HasPrefix:  true`
`HasSuffix:  true`
`Index:      1`
`Join:       a-b`
`Repeat:     aaaaa`
`Replace:    f00`
`Replace:    f0o`
`Split:      [a b c d e]`
`ToLower:    test`
`ToUpper:    TEST`

___

##### Run Command:

`$ wasmtk info string-functions.wasm`
