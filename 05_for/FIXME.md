## Compilation Error

**Error:** `f64.rem` unexpected token in WAT  
**Root cause:** `%` on `number` type emits `f64.rem`, which is invalid WAT syntax  
**Fix needed:** Change loop variables `n`, `j` to `i32` type, or replace `n % 2 === 0` with an integer-based check
