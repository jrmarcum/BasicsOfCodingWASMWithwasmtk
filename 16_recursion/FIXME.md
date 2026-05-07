## Compilation Error

**Error:** `undefined function variable "$fib"` in WAT  
**Root cause:** `const fib = function(n) { ... fib(n-1) ... }` — anonymous self-referencing function stored in a variable is not registered as a callable symbol by wasic  
**Fix needed:** Convert `const fib = function(...)` to a named `function fib(...)` declaration
