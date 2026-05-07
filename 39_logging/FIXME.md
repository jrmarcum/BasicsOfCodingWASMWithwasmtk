## Compilation Error

**Error:** `undefined local variable "$TIMESTAMP"` in WAT  
**Root cause:** wasic emits `local.get $TIMESTAMP` instead of a global read when a module-level `string` constant is used inside a named function body via template literal  
**Fix needed:** Pass `TIMESTAMP` as a parameter to `stdLog`/`myLog`, or inline the string literal directly in the function
