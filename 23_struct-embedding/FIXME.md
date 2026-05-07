## Compilation Error

**Error:** `undefined function variable "$descFn"` in WAT  
**Root cause:** `const descFn: () => string = () => containerDescribe(co)` — an arrow function stored in a typed variable and then called as `descFn()` is not recognized as a callable by wasic  
**Fix needed:** Replace the arrow-function variable with a direct call: `console.log("describer:", containerDescribe(co))`
