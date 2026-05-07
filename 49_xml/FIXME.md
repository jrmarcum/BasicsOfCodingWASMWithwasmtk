## Compilation Error

**Error:** `undefined local variable "$s"` in WAT  
**Root cause:** String accumulator scoping issue in an XML-builder function that uses template-literal concatenation with an `indent: number` variable — wasic fails to declare `$s` as a local in this context  
**Fix needed:** Restructure the string building to avoid mixed numeric/string template literals in the accumulation loop, or split into simpler steps
