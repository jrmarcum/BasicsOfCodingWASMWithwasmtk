## Compilation Error

**Error:** `undefined local variable "$result"` in WAT  
**Root cause:** String accumulator scoping issue in a header-formatting loop that accesses `hdrs[i].name` and `hdrs[i].value` fields via template literal — wasic fails to declare `$result` as a local  
**Fix needed:** Pre-declare `result` as a simple string variable, or restructure the header formatting to avoid template-literal struct-field access inside the loop
