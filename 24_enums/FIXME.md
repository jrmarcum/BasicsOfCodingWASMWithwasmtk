## Compilation Error

**Error:** `pop from empty stack / beyond block start boundary` in WASM binary parser  
**Root cause:** wasic produces malformed WAT for a `switch` on an enum value combined with `throw new Error(...)` in the default case  
**Fix needed:** Replace the `throw` in the default case with `console.log(...)` and `return`, or rewrite as an if/else chain
