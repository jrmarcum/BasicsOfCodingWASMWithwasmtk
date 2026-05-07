#### WebAssembly has no timer or ticker API. This lesson uses static timestamps to represent Go's `time.NewTicker(50ms)` ticking three times before `ticker.Stop()` is called. In production WASM environments, tickers would be driven by a host-provided clock import.
___
##### Run Command:

`$ wasmtk run tickers.ts`

##### Results:

`Tick at 2009-11-10T23:00:00.000Z`
`Tick at 2009-11-10T23:00:00.050Z`
`Tick at 2009-11-10T23:00:00.100Z`
`Ticker stopped`

___

##### Run Command:

`$ wasmtk wasic tickers.ts`

`$ wasmtk run tickers.wasm`

##### Results:

`Tick at 2009-11-10T23:00:00.000Z`
`Tick at 2009-11-10T23:00:00.050Z`
`Tick at 2009-11-10T23:00:00.100Z`
`Ticker stopped`

___

##### Run Command:

`$ wasmtk info tickers.wasm`
