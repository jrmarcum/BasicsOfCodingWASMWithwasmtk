## Compilation Error

**Error:** `undefined local variable "$s"` and `"$pStr"` in WAT  
**Root cause:** Same string-accumulator scoping issue as 40_sorting; also affects `pStr` built from a `Person[]` struct array with template literal interpolation  
**Fix needed:** Same fix as 40_sorting — investigate string accumulator declaration with struct array element access in loops
