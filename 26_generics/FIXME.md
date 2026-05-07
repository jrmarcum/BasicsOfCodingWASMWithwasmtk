## Compilation Error

**Error:** `'listNodes' is not defined — 'listNodes.push(...)' cannot be compiled`  
**Root cause:** wasic does not allow a module-level struct array (`NumNode[]`) to be accessed inside named function bodies  
**Fix needed:** Pass `listNodes` as a parameter to each function, or restructure to avoid global struct-array mutation from inside functions
