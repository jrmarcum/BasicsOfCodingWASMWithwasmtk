## Compilation Error

**Error:** `unexpected token string, expected )` — ternary with string result type in WAT  
**Root cause:** `return condition ? "true" : "false"` emits `(if (result string) ...)` in WAT, which the WAT parser rejects — wasic cannot use string as an `if` result type  
**Fix needed:** Replace the ternary with an explicit `if/else` block that assigns to a string variable, then return the variable
