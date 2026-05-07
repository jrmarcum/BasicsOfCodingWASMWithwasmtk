## Compilation Error

**Error:** `f64.rem` unexpected token in WAT  
**Root cause:** `(i % 3)` where `i: number` emits `f64.rem`, which is invalid WAT syntax  
**Fix needed:** Change `i` to `i32` type, or compute `workerId` with integer arithmetic (e.g., a lookup table or explicit if/else)
