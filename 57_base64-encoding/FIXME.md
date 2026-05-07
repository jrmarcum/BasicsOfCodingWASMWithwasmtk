## Compilation Error

**Error:** `'console' is not defined — 'console.log(...)' cannot be compiled`  
**Root cause:** `console.log()` called with zero arguments is not handled by wasic — same issue as 22_strings-and-runes  
**Fix needed:** Replace bare `console.log()` with `console.log("")`
