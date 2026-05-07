## Compilation Error

**Error:** `undefined local variable "$ops"` in WAT (inside nested for loop)  
**Root cause:** wasic emits `local.set $ops` instead of a global set when a module-level `number` variable is mutated inside a nested `for` loop body  
**Fix needed:** Wrap the loop logic in a function with `ops` as a local variable, or restructure to avoid module-level variable mutation inside nested loops
