## Compilation Error

**Error:** `undefined local variable "$s"` and `"$twoDStr"` in WAT  
**Root cause:** wasic fails to emit local declarations for string accumulator variables used inside loops with template-literal concatenation when the array element type is `number[]`  
**Fix needed:** Restructure string building to avoid template literals inside the loop, or use a helper function that wasic can compile cleanly
