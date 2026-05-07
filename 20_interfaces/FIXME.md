## Compilation Error

**Error:** `pop from empty stack / beyond block start boundary` in WASM binary parser  
**Root cause:** wasic produces malformed WAT for a function with multiple early `return` statements gated on a `string` field comparison (`g.kind === "rect"`)  
**Fix needed:** Rewrite `area`/`perim`/`geomStr` as if/else chains instead of multiple early returns, or use a numeric discriminator instead of a string `kind` field
