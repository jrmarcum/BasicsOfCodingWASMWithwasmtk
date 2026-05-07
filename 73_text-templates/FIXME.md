## Compilation Error

**Error:** `undefined local variable "$s"` and `"$rangeOut"` in WAT  
**Root cause:** String accumulator scoping issues in the `join`-style helper (same as 45_string-functions) and in the range-rendering loop over a `string[]` with struct-field interpolation  
**Fix needed:** Same fix as 45_string-functions; also restructure the range renderer to avoid the `$rangeOut` accumulator pattern that wasic cannot compile
