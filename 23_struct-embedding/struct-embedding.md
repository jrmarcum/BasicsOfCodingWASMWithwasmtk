#### Go struct embedding is implemented with composition — a `Container` struct holds a `Base` struct and promotes its fields via explicit delegation. Field access uses `co.base.num` rather than Go's promoted `co.num`.
___
##### Run Command:

`$ wasmtk run struct-embedding.ts`

##### Results:

`co={num: 1, str: some name}`
`also num: 1`
`describe: base with num=1`
`describer: base with num=1`

___

##### Run Command:

`$ wasmtk wasic struct-embedding.ts`

`$ wasmtk run struct-embedding.wasm`

##### Results:

`co={num: 1, str: some name}`
`also num: 1`
`describe: base with num=1`
`describer: base with num=1`

___

##### Run Command:

`$ wasmtk info struct-embedding.wasm`
