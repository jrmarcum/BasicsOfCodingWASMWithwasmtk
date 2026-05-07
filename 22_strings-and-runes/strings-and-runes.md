#### wasic has no `codePointAt` method or byte-buffer API. This lesson hard-codes the UTF-8 byte sequence and Unicode code points for the Thai string `"สวัสดี"` (18 bytes, 6 runes), matching the Go output exactly.
___
##### Run Command:

`$ wasmtk run strings-and-runes.ts`

##### Results:

`Len: 18`
`e0 b8 aa e0 b8 a7 e0 b8 b1 e0 b8 aa e0 b8 94 e0 b8 b5 `
`Rune count: 6`
`U+0E2A 'ส' starts at 0`
`U+0E27 'ว' starts at 3`
`U+0E31 'ั' starts at 6`
`U+0E2A 'ส' starts at 9`
`U+0E14 'ด' starts at 12`
`U+0E35 'ี' starts at 15`

`Using explicit decoding`
`U+0E2A 'ส' starts at 0`
`found so sua`
`U+0E27 'ว' starts at 3`
`U+0E31 'ั' starts at 6`
`U+0E2A 'ส' starts at 9`
`found so sua`
`U+0E14 'ด' starts at 12`
`U+0E35 'ี' starts at 15`

___

##### Run Command:

`$ wasmtk wasic strings-and-runes.ts`

`$ wasmtk run strings-and-runes.wasm`

##### Results:

`Len: 18`
`e0 b8 aa e0 b8 a7 e0 b8 b1 e0 b8 aa e0 b8 94 e0 b8 b5 `
`Rune count: 6`
`U+0E2A 'ส' starts at 0`
`U+0E27 'ว' starts at 3`
`U+0E31 'ั' starts at 6`
`U+0E2A 'ส' starts at 9`
`U+0E14 'ด' starts at 12`
`U+0E35 'ี' starts at 15`

`Using explicit decoding`
`U+0E2A 'ส' starts at 0`
`found so sua`
`U+0E27 'ว' starts at 3`
`U+0E31 'ั' starts at 6`
`U+0E2A 'ส' starts at 9`
`found so sua`
`U+0E14 'ด' starts at 12`
`U+0E35 'ี' starts at 15`

___

##### Run Command:

`$ wasmtk info strings-and-runes.wasm`
