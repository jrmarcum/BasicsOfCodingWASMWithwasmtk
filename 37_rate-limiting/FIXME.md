## Compilation Error

**Error:** `undefined local variable "$tokens"` in WAT (inside for loop)  
**Root cause:** wasic emits `local.set $tokens` instead of a global set when a module-level `number` variable is decremented (`tokens--`) inside a `for` loop body  
**Fix needed:** Wrap the loop in a function with `tokens` as a local variable, or restructure to avoid module-level mutation inside loops
