## Compilation Error

**Error:** Binaryen internal abort — `invalid type UNREACHABLE`  
**Root cause:** `%` on `number` literals (e.g., `7 % 2`) emits `f64.rem`, triggering a Binaryen optimizer crash  
**Fix needed:** Replace `7 % 2 === 0` etc. with pre-computed boolean literals or use `i32` typed variables
