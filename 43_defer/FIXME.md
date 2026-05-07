## Compilation Error

**Error:** `'deferred' is not defined — 'deferred.push(...)' cannot be compiled`  
**Root cause:** `Array<() => void>` — wasic does not support arrays of function types; the module-level `deferred` array of closures cannot be compiled  
**Fix needed:** Rewrite without a function array; simulate deferred LIFO output by capturing values in a plain array and printing in reverse
