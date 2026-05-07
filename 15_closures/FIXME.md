## Compilation Error

**Error:** `Unknown function 'intSeq' — not declared in this module`  
**Root cause:** wasic does not support functions that return a function value (`(): () => number`); the returned inner function cannot be stored and called through a variable  
**Fix needed:** Rewrite using a module-level counter and a regular function, removing the closure/function-return pattern
