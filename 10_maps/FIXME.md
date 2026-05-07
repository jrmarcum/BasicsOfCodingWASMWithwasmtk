## Compilation Error

**Error:** `'mKeys' is not defined — 'mKeys.push(...)' cannot be compiled`  
**Root cause:** wasic does not allow module-level `string[]` arrays to be accessed (`.push`, `.length`, indexing) inside named function bodies  
**Fix needed:** Pass `mKeys`/`mVals` as parameters, or restructure to avoid global array mutation from inside functions
