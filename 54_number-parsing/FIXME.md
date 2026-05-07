## Compilation Error

**Error:** `Unknown function 'isNaN' — not declared in this module`  
**Root cause:** `isNaN()` is not available in wasic; the compiler does not recognize it as a built-in  
**Fix needed:** Remove the `isNaN` call; since the parse result is hardcoded, replace with an explicit boolean or remove the error-check branch entirely
