## Compilation Error

**Error:** `pop from empty stack / beyond block start boundary` in WASM binary parser  
**Root cause:** wasic produces malformed WAT for the file-paths implementation, likely due to the combination of multiple string-slice helper functions with early returns and string comparisons  
**Fix needed:** Simplify the helper functions; avoid multiple early returns from string-returning functions, and test each helper in isolation to identify the exact trigger
