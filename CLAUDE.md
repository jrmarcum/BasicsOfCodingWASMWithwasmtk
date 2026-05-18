# Basics of Coding WASM with wasmtk — Project Context

## Purpose

Multi-language comparative study of programming syntax, language simplicity,
lines of code required, and runtime performance. WebAssembly (via wasmtk) is
one of several languages implemented against the same set of example programs,
enabling direct side-by-side comparison.

## Licensing Summary

This project contains two tiers of content with different licenses:

- **CC BY 3.0** — lesson files and code examples adapted from
  "Basics of Coding Go" by Jon Marcum, which was itself adapted from
  "Go by Example" by Mark McGranaghan
  (https://github.com/mmcgrana/gobyexample).
  License: http://creativecommons.org/licenses/by/3.0/

- **CC0 1.0** — original contributions by Jon Marcum (project structure,
  README, comparative-study additions, and any lessons not derived from
  Go by Example). See LICENSE.

Attribution for derived content is provided centrally in README.md and
NOTICE — do **not** add a per-file attribution footer to lesson `.md` files.

## Upstream Reference

BasicsOfCodingGo is included as a git submodule at `upstream/basicsofcodinggo`.
Read each lesson from `upstream/basicsofcodinggo/##_topic-name/` as the
source of truth for program logic and expected output.

## Project Structure

```
BasicsOfCodingWASMWithwasmtk/
├── CLAUDE.md          — this file; canonical project context for Claude sessions
├── LICENSE            — CC0 (applies to Jon Marcum's original contributions)
├── NOTICE             — attribution notice for CC BY 3.0 derived content
├── README.md          — project overview, attribution section, license table
├── upstream/
│   └── basicsofcodinggo/  — git submodule: BasicsOfCodingGo reference
└── ##_topic-name/
    ├── topic-name.ts  — TypeScript source (compiled to WASM via wasmtk wasic)
    └── topic-name.md  — lesson explanation (run commands + expected output)
```

Lessons are numbered with a two-digit prefix (e.g., `01_hello-world`),
mirroring BasicsOfCodingGo exactly: same lesson numbers, same folder names.

## Toolchain

wasmtk is a WebAssembly Development Toolkit published on JSR at
`jsr:@jrmarcum/wasmtk`. Install with:

```
deno install -g -A jsr:@jrmarcum/wasmtk
```

The primary command used in this project is:

```
wasmtk run <file.ts>
```

This invokes the `wasic` compilation path:
`.ts → WasicTranspiler → WAT → Binaryen (-Oz) → .wasm → wasmtime/wasmer`

Producing a standalone WASI module with no embedded JavaScript runtime.

Other useful commands:
- `wasmtk wasic <file.ts>` — compile only, produces `<file>.wasm`
- `wasmtk run <file.wasm>` — run a pre-compiled WASM module
- `wasmtk info <file.wasm>` — inspect exported functions

## TypeScript Subset Supported by wasic

The wasic transpiler compiles a specific subset of TypeScript to WebAssembly
Text Format (WAT). Supported features include:

**Functions & Variables**
- `function` declarations with typed params (`number`, `string`, `boolean`,
  `i32`, `i64`, `f32`, `f64`)
- `let`, `const`, `var` declarations
- Default and optional parameters
- Arrow functions: `const fn = (x: number): number => x * 2`
- First-class function variables: `const op: (a: number, b: number) => number = add`
- Closure capture (outer-scope variables injected as hidden params)
- `return` statements

**Control Flow**
- `if` / `else if` / `else`
- `while` / `do-while`
- `for (init; cond; update)`
- `switch` / `case` / `default` / `break` / fallthrough
- Labeled break and continue: `outer: for(...) { break outer; }`
- Ternary: `cond ? a : b`

**Types**
- Numeric: `i32`, `i64`, `f32`, `f64`, `number`, `boolean`
- Strings: stored in linear memory as ptr+len pairs
- Template literals with interpolation: `` `x=${x}` ``
- Numeric enums: `enum Dir { Up = 0, Down = 1 }`

**Structs (via interfaces)**
- `interface` declarations as struct definitions
- Struct literals: `const v: Vec2 = { x: 1.0, y: 2.0 }`
- Field read/write: `v.x`, `v.y = 3.0`
- Object destructuring: `const { x, y } = vec`

**Arrays**
- Static: `i32[]`, `f64[]` with literal initializer
- Dynamic: heap-allocated; `push`, `pop`, `shift`, `unshift`, `slice`
- Also: `indexOf`, `includes`, `forEach`, `map`, `filter`, `find`, `reduce`
- Rest parameters: `function f(...args: i32[])`
- Spread: `f(...arr)`, `[...a, ...b]`

**Math**
- `Math.sqrt`, `Math.abs`, `Math.pow`, `Math.floor`, `Math.ceil`, `Math.round`
- `Math.min`, `Math.max`, `Math.sign`, `Math.trunc`

**Exception Handling**
- `throw new Error("msg")`, `throw "literal"`, `throw someVar`
- `try { } catch (e) { }`, `try { } finally { }`, combined form

**Multi-file**
- Relative imports: `import { foo } from "./lib.ts"` (via tsbundler)

**Console I/O**
- `console.log(...)`, `console.error(...)`, `console.warn(...)` — all write to stdout/stderr
- `console.log()` with zero arguments is **not** supported — use `console.log("")`

**Not supported in wasic (use note in .md)**
- `for...of`, `for...in` — use indexed `for` loops instead
- `Object.keys()`, `Object.entries()` — use parallel arrays or manual lookup
- `new Array()`, `Array.prototype.fill()` — use literal initializers
- `Array.join()` — build strings manually in a loop
- Classes — use `interface` + factory functions
- `Math.random()` — use a seeded LCG/mulberry32 PRNG
- `Math.sin()`, `Math.cos()`, `Math.tan()` — may or may not work via Binaryen
- `Date` object — no time API; use static example values
- `JSON.parse()` / `JSON.stringify()` — build/parse strings manually
- `RegExp` — implement simple pattern matching
- `URL` API — parse strings manually
- `parseInt()` / `parseFloat()` — implement manually or use typed conversion
- `isNaN()` — not available; avoid or replace with explicit checks
- `String.fromCharCode()` — not available; use `.charCodeAt()` for inspection
- `crypto` module — implement algorithms manually or note not available
- Network APIs (`fetch`, `http`, `net`) — not available in WASI
- Process APIs (`exec`, `spawn`, signals) — not available in WASI
- Custom exit codes — `proc_exit` always exits 0; cannot set a non-zero exit code from TypeScript
- `Deno.*` APIs — use `console.log` directly
- Union types (`A | B`) — use struct with discriminator field

## .gitignore

The project `.gitignore` covers:

```gitignore
# Compiled WASM binaries produced by wasmtk wasic
*.wasm

# Temporary files created by lesson examples (lessons 58-60)
tmp/

# Deno cache
.deno/

# Environment files
.env
.env.local

# OS artifacts
.DS_Store
Thumbs.db
```

## Language Notes for Future Claude Sessions

- **Runtime:** wasmtk `wasic` path. No Node.js, no browser. Pure WASI.
- **Run command:** `wasmtk run filename.ts` (compiles + runs in one step)
- **Output format:** For complex types (arrays, maps), format output manually
  to match Go's output format (`[a b c]`, `map[k:v]`), since wasic's
  `console.log` formatting for aggregate types is implementation-defined.
- **No classes:** Translate all class-based patterns to `interface` + factory
  function, matching wasic's struct model.
- **No `for...of`:** Use indexed `for` loops: `for (let i = 0; i < n; i++)`.
- **No Object.keys/entries:** Use parallel arrays (keys[], vals[]) for
  map-like structures.
- **Concurrency lessons (27-37):** WebAssembly is single-threaded; implement
  sequential equivalents and add a description note to the `.md` file.
- **Networking lessons (69-72):** Not available in WASI; note in `.md` and
  show the concept with a simplified sequential simulation.
- **Process lessons (74-76):** Not available in WASI; note in `.md`.
- **Date/time lessons (50-52):** No `Date` API; use static example values
  with a note that output is fixed (not time-dependent).
- **Random numbers (53):** Use mulberry32 PRNG with seed 42 for all outputs
  (no `Math.random()`). All output is deterministic.
- **String iteration (11, 22):** No `codePointAt()` in wasic; use known
  code-point values as constants, or note the limitation.
- **Lessons with setup steps:** 58 (reading-files — run 59 first to create
  `tmp/dat`), 60 (line-filters — requires stdin piping).

## Per-Lesson Implementation Strategy (Unavailable Features)

Lessons where WASI/wasic limitations require workarounds:

- **58 (reading-files):** Hardcoded simulation of reading `tmp/dat`; description note explains WASI has no file-read API.
- **59 (writing-files):** Hardcoded simulation; prints the bytes-written counts that Go would produce.
- **60 (line-filters):** No stdin in WASI; hardcoded input lines processed through the filter logic; description note.
- **61 (file-paths):** Fully implemented using `charCodeAt`/`slice`/`startsWith`/`endsWith`; path normalization and `rel()` hardcoded.
- **62 (directories):** Hardcoded simulation of directory listing output.
- **63 (temporary-files):** Hardcoded simulation; path in output varies, noted in `.md`.
- **64 (command-line-arguments):** Hardcoded demo values; description note explains no `args` access in WASI.
- **65 (command-line-flags):** Hardcoded demo values with description note.
- **66 (command-line-subcommands):** Hardcoded demo values with description note.
- **67 (environment-variables):** Hardcoded demo values; description note that env access is not available in WASI.
- **68 (testing-and-benchmarking):** Manual test runner implemented in TypeScript, mimicking `go test -v` output format.
- **69 (http-client):** HTTP not available in WASI; description note + minimal sequential simulation.
- **70 (http-server):** HTTP not available in WASI; description note + prints simulated request/response.
- **71 (context):** Context cancellation not available; description note + sequential simulation.
- **72 (tcp-server):** TCP not available in WASI; description note + `toUpperCase` echo demo.
- **73 (text-templates):** Implemented using `str.replace()` for `{{.}}` and `{{.Name}}`; if/else and range blocks hardcoded.
- **74 (execing-processes):** Not available in WASI; description note + single explanatory `console.log`.
- **75 (spawning-processes):** Not available in WASI; description note + single explanatory `console.log`.
- **76 (signals):** Signal handling not available in WASI; description note showing expected output for `SIGINT`.
- **77 (exit):** Custom exit codes not supported (`proc_exit` always exits 0); prints `exit status 3` to demonstrate the concept.
- **78 (sha256-hashes):** No crypto API; SHA256 of `"sha256 this string"` is pre-computed and hard-coded.

## Variable Output Lessons

These lessons produce output that varies or is implementation-defined;
note this in the `.md` description:
- 07 (switch — day/hour use static values)
- 39 (logging — timestamp is static placeholder)
- 50 (time — static example values)
- 51 (epoch — static example values)
- 52 (time-formatting-parsing — static example values)
- 63 (temporary-files — path varies)
- 67 (environment-variables — env keys vary)
- 74 (execing-processes — version varies)
- 75 (spawning-processes — version varies)

## .md File Format

Each lesson `.md` follows the Go/V reference format:

```
#### Optional description (language note or setup instruction).
___
##### Run Command:

`$ wasmtk run filename.ts`

##### Results:

`output line 1`
`output line 2`
```

Rules:
- The description line (if present) is a single `####` sentence before the first `___`.
- No opening `___` before a description; `___` separates description from run command.
- If there is no description, the file starts directly with `##### Run Command:`.
- Multiple run command sections are separated by a blank line, `___`, and a blank line.
- No per-file attribution footer — attribution is fully satisfied by README and NOTICE.
