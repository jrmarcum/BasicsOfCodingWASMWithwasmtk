## Compilation Error

**Error:** `undefined local variable "$s"` in WAT  
**Root cause:** String accumulator scoping issue in a helper that formats a `string[]` — same pattern as 40_sorting; wasic fails to declare `$s` as a local when the loop body accesses `string[]` elements  
**Fix needed:** Same fix as 40_sorting
