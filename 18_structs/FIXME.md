## Compilation Error

**Error:** `pop from empty stack / beyond block start boundary` in WASM binary parser  
**Root cause:** wasic produces malformed WAT for a struct with a `boolean` field (`isGood`) combined with a template-literal format string using that field  
**Fix needed:** Investigate whether `boolean` struct fields in template literals trigger the issue; may need to convert `boolean` to `i32` or format `isGood` separately
