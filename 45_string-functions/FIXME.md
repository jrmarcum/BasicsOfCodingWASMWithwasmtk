## Compilation Error

**Error:** `undefined local variable "$r"` and `"$s"` in WAT  
**Root cause:** String accumulator scoping issue in a custom `join`/`split` implementation — wasic fails to declare string-builder variables as locals when array element access is combined with `.slice()` calls in the loop  
**Fix needed:** Investigate and simplify the string-building pattern; may need to avoid `.slice()` return values being concatenated inline
