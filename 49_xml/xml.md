#### wasic TypeScript has no XML parser. This lesson uses string building for XML generation and manual field access for "parsing", reproducing the same Go output without a third-party library.
___
##### Run Command:

`$ wasmtk run xml.ts`

##### Results:

` <plant id="27">`
`   <name>Coffee</name>`
`   <origin>Ethiopia</origin>`
`   <origin>Brazil</origin>`
` </plant>`
`<?xml version="1.0" encoding="UTF-8"?>`
` <plant id="27">`
`   <name>Coffee</name>`
`   <origin>Ethiopia</origin>`
`   <origin>Brazil</origin>`
` </plant>`
`Plant id=27, name=Coffee, origin=[Ethiopia Brazil]`
` <nesting>`
`   <parent>`
`     <child>`
`       <plant id="27">`
`         <name>Coffee</name>`
`         <origin>Ethiopia</origin>`
`         <origin>Brazil</origin>`
`       </plant>`
`       <plant id="81">`
`         <name>Tomato</name>`
`         <origin>Mexico</origin>`
`         <origin>California</origin>`
`       </plant>`
`     </child>`
`   </parent>`
` </nesting>`

___

##### Run Command:

`$ wasmtk wasic xml.ts`

`$ wasmtk run xml.wasm`

##### Results:

` <plant id="27">`
`   <name>Coffee</name>`
`   <origin>Ethiopia</origin>`
`   <origin>Brazil</origin>`
` </plant>`
`<?xml version="1.0" encoding="UTF-8"?>`
` <plant id="27">`
`   <name>Coffee</name>`
`   <origin>Ethiopia</origin>`
`   <origin>Brazil</origin>`
` </plant>`
`Plant id=27, name=Coffee, origin=[Ethiopia Brazil]`
` <nesting>`
`   <parent>`
`     <child>`
`       <plant id="27">`
`         <name>Coffee</name>`
`         <origin>Ethiopia</origin>`
`         <origin>Brazil</origin>`
`       </plant>`
`       <plant id="81">`
`         <name>Tomato</name>`
`         <origin>Mexico</origin>`
`         <origin>California</origin>`
`       </plant>`
`     </child>`
`   </parent>`
` </nesting>`

___

##### Run Command:

`$ wasmtk info xml.wasm`
