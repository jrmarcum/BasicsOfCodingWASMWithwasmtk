#### Go's `log` and `log/slog` packages are simulated with plain `console.log` calls. Timestamps use the fixed Go playground reference time `2009/11/10 23:00:00`; actual timestamps would vary with each run.
___
##### Run Command:

`$ wasmtk run logging.ts`

##### Results:

`2009/11/10 23:00:00 standard logger`
`2009/11/10 23:00:00 with micro`
`2009/11/10 23:00:00 with file/line`
`2009/11/10 23:00:00 my:from mylog`
`2009/11/10 23:00:00 ohmy:from mylog`
`from buflog:2009/11/10 23:00:00 buf:hello`
``
`{"time":"2009/11/10 23:00:00","level":"INFO","msg":"hi there"}`
`{"time":"2009/11/10 23:00:00","level":"INFO","msg":"hello again","key":"val","age":25}`

___

##### Run Command:

`$ wasmtk wasic logging.ts`

`$ wasmtk run logging.wasm`

##### Results:

`2009/11/10 23:00:00 standard logger`
`2009/11/10 23:00:00 with micro`
`2009/11/10 23:00:00 with file/line`
`2009/11/10 23:00:00 my:from mylog`
`2009/11/10 23:00:00 ohmy:from mylog`
`from buflog:2009/11/10 23:00:00 buf:hello`
``
`{"time":"2009/11/10 23:00:00","level":"INFO","msg":"hi there"}`
`{"time":"2009/11/10 23:00:00","level":"INFO","msg":"hello again","key":"val","age":25}`

___

##### Run Command:

`$ wasmtk info logging.wasm`
