##### Run Command:

`$ wasmtk run testing-and-benchmarking.ts`

##### Results:

`=== RUN   TestIntMinBasic`
`--- PASS: TestIntMinBasic (0.00s)`
`=== RUN   TestIntMinTableDriven`
`=== RUN   TestIntMinTableDriven/0,1`
`=== RUN   TestIntMinTableDriven/1,0`
`=== RUN   TestIntMinTableDriven/2,-2`
`=== RUN   TestIntMinTableDriven/0,-1`
`=== RUN   TestIntMinTableDriven/-1,0`
`--- PASS: TestIntMinTableDriven (0.00s)`
`    --- PASS: TestIntMinTableDriven/0,1 (0.00s)`
`    --- PASS: TestIntMinTableDriven/1,0 (0.00s)`
`    --- PASS: TestIntMinTableDriven/2,-2 (0.00s)`
`    --- PASS: TestIntMinTableDriven/0,-1 (0.00s)`
`    --- PASS: TestIntMinTableDriven/-1,0 (0.00s)`
`PASS`
`ok  	main	0.023s`

___

##### Run Command:

`$ wasmtk wasic testing-and-benchmarking.ts`

`$ wasmtk run testing-and-benchmarking.wasm`

##### Results:

`=== RUN   TestIntMinBasic`
`--- PASS: TestIntMinBasic (0.00s)`
`=== RUN   TestIntMinTableDriven`
`=== RUN   TestIntMinTableDriven/0,1`
`=== RUN   TestIntMinTableDriven/1,0`
`=== RUN   TestIntMinTableDriven/2,-2`
`=== RUN   TestIntMinTableDriven/0,-1`
`=== RUN   TestIntMinTableDriven/-1,0`
`--- PASS: TestIntMinTableDriven (0.00s)`
`    --- PASS: TestIntMinTableDriven/0,1 (0.00s)`
`    --- PASS: TestIntMinTableDriven/1,0 (0.00s)`
`    --- PASS: TestIntMinTableDriven/2,-2 (0.00s)`
`    --- PASS: TestIntMinTableDriven/0,-1 (0.00s)`
`    --- PASS: TestIntMinTableDriven/-1,0 (0.00s)`
`PASS`
`ok  	main	0.023s`

___

##### Run Command:

`$ wasmtk info testing-and-benchmarking.wasm`
