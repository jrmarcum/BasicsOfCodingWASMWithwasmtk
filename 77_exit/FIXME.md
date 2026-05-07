## Compilation Error

**Error:** `'deferred' is not defined — 'deferred.push(...)' cannot be compiled`  
**Root cause:** `Array<() => void>` — wasic does not support arrays of function types; same issue as 43_defer  
**Fix needed:** Remove the function array; since this lesson only needs to show exit status, simplify to just `console.log("exit status 3")` without the deferred pattern
