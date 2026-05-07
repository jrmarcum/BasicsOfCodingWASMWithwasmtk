## Compilation Error

**Error:** `undefined local variable "$s"` and `"$twoDStr"` in WAT  
**Root cause:** Same as 08_arrays — wasic fails to emit local declarations for string accumulator variables used with template-literal concatenation inside loops over `number[]` arrays  
**Fix needed:** Restructure string building helpers or avoid template literals inside the accumulation loop
