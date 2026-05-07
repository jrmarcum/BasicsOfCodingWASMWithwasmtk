## Compilation Error

**Error:** `Unknown function 'r1'`, `'r3'`, `'r4'`, `'r5'` — not declared in this module  
**Root cause:** Arrow functions stored in variables (e.g., `const r1 = () => mulberry32()`) are not recognized as callable symbols when invoked — same limitation as 15_closures and 23_struct-embedding  
**Fix needed:** Convert `const r1 = ...` arrow function variables to named `function r1()` declarations
