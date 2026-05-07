## Compilation Error

**Error:** Binaryen abort — `Assertion failed: binary->type.isInteger()`  
**Root cause:** Binaryen optimizer fails on a nested struct literal in a return statement (`argErr: { arg, prob: "..." }`) combined with a `boolean` field, likely a type-inference issue in wasic's WAT emission  
**Fix needed:** Flatten the nested struct (split `ArgError` fields into `Result2` directly), or avoid the nested struct literal in the return expression
