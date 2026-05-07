## Compilation Error

**Error:** Binaryen internal abort — `invalid type UNREACHABLE`  
**Root cause:** Binaryen optimizer crashes on the test runner implementation, likely due to a comparison expression involving struct field access combined with a boolean condition in the test loop  
**Fix needed:** Simplify the test runner; avoid complex boolean expressions or struct-field comparisons that trigger the Binaryen optimizer bug
