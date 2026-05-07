#### wasic has no `Math.random()`; all random values use the mulberry32 seeded PRNG with seed 42. All output is deterministic. `Math.imul` provides 32-bit integer multiplication required by the PRNG.
___
##### Run Command:

`$ wasmtk run random-numbers.ts`

##### Results:

`56,17`
`0.13153778833244741`
`5.657688941620290,5.085012853611260`
`56,17`
`56,17`

___

##### Run Command:

`$ wasmtk wasic random-numbers.ts`

`$ wasmtk run random-numbers.wasm`

##### Results:

`56,17`
`0.13153778833244741`
`5.657688941620290,5.085012853611260`
`56,17`
`56,17`

___

##### Run Command:

`$ wasmtk info random-numbers.wasm`
