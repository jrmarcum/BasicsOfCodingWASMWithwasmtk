## Compilation Error

**Error:** `'console' is not defined — 'console.log(...)' cannot be compiled`  
**Root cause:** `console.log()` called with zero arguments (line 18) is not handled by wasic; it cannot emit a call with no string argument  
**Fix needed:** Replace bare `console.log()` with `console.log("")` to provide an empty string argument
