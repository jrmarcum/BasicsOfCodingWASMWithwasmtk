## Compilation Error

**Error:** `unexpected token string, expected )` — ternary with string result type in WAT  
**Root cause:** `return idx >= 0 ? u.slice(0, idx) : ""` emits `(if (result string) ...)` in WAT, which the WAT parser rejects — same issue as 48_json  
**Fix needed:** Replace ternary string returns with explicit `if/else` blocks that assign to a variable, then return the variable
