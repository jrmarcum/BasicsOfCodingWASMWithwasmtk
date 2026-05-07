## Compilation Error

**Error:** Binaryen abort — `Assertion failed: binary->type.isInteger()`  
**Root cause:** Binaryen optimizer fails on an expression mixing string-pointer arithmetic with a `number` (f64) array index, likely from `sum += nums[idx]` where `nums: number[]` and `sum: number`  
**Fix needed:** Type `sum` and `idx` as `i32`, or restructure to avoid the mixed-type expression that triggers the optimizer assertion
