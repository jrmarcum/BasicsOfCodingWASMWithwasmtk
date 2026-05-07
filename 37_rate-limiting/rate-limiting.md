#### WebAssembly has no timer API; timestamps are static. This lesson shows Go's channel-ticker rate limiter concept: a throttled loop (one request per 20 ms slot) and a bursty loop (3 immediate + 2 throttled), using fixed timestamps.
___
##### Run Command:

`$ wasmtk run rate-limiting.ts`

##### Results:

`request 1 2009-11-10T23:00:00.000Z`
`request 2 2009-11-10T23:00:00.000Z`
`request 3 2009-11-10T23:00:00.000Z`
`request 4 2009-11-10T23:00:00.000Z`
`request 5 2009-11-10T23:00:00.000Z`
`request 1 2009-11-10T23:00:00.000Z`
`request 2 2009-11-10T23:00:00.000Z`
`request 3 2009-11-10T23:00:00.000Z`
`request 4 2009-11-10T23:00:00.020Z`
`request 5 2009-11-10T23:00:00.020Z`

___

##### Run Command:

`$ wasmtk wasic rate-limiting.ts`

`$ wasmtk run rate-limiting.wasm`

##### Results:

`request 1 2009-11-10T23:00:00.000Z`
`request 2 2009-11-10T23:00:00.000Z`
`request 3 2009-11-10T23:00:00.000Z`
`request 4 2009-11-10T23:00:00.000Z`
`request 5 2009-11-10T23:00:00.000Z`
`request 1 2009-11-10T23:00:00.000Z`
`request 2 2009-11-10T23:00:00.000Z`
`request 3 2009-11-10T23:00:00.000Z`
`request 4 2009-11-10T23:00:00.020Z`
`request 5 2009-11-10T23:00:00.020Z`

___

##### Run Command:

`$ wasmtk info rate-limiting.wasm`
