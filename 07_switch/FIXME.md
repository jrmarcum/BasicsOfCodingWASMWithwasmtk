## Compilation Error

**Error:** `pop from empty stack / beyond block start boundary` in WASM binary parser  
**Root cause:** wasic switch codegen produces malformed WAT when a `switch` contains only `case`/`break` with string assignment to a pre-declared variable  
**Fix needed:** Rewrite switch as if/else chain, or inline the string assignment directly
