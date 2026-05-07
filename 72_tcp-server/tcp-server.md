#### TCP networking is not available in WASI; this lesson demonstrates the message-echo concept with a direct function call.
___
##### Run Command:

`$ wasmtk run tcp-server.ts`

##### Results:

`ACK: HELLO TCP`

___

##### Run Command:

`$ wasmtk wasic tcp-server.ts`

`$ wasmtk run tcp-server.wasm`

##### Results:

`ACK: HELLO TCP`

___

##### Run Command:

`$ wasmtk info tcp-server.wasm`
