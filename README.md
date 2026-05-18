# Basics of Coding WASM with wasmtk

## Preface

What this text is and what it is not: This text is intended to introduce the reader to the basics of WebAssembly programming in the sense that they will be able to write minimal types of programs and compile and run them as WASM modules. It is not intended to go into advanced topics like multi-threading, shared memory, SIMD, or WebAssembly component model.

The programs are intended to be run in the terminal as that is common to most operating systems. Linux and Mac come preinstalled with a terminal. Windows may or may not have it pre-installed. "Windows Terminal" can be installed from the Microsoft store. Just do a search for it and install it.

## Installation and Setup of wasmtk

To set up wasmtk, install [Deno](https://deno.com/) first, then install wasmtk from JSR:

```sh
deno install -g -A jsr:@jrmarcum/wasmtk
```

If wasmtk has been installed properly you will be able to type the following command in the terminal command line and receive the response shown:

```sh
wasmtk --version
wasmtk v1.5.4
(Note: the version shown here varies with your installed version)
```

## How to Run Examples

Each lesson folder contains a `.ts` (TypeScript) source file and a `.md` file showing the run command and expected output. wasmtk compiles the TypeScript to a standalone WASI module and runs it — no separate compilation step needed.

Navigate into the lesson folder and run with `wasmtk run`:

```sh
cd 01_hello-world
wasmtk run hello-world.ts
hello world
```

You can also compile to a `.wasm` binary first and then run it separately — the output is identical:

```sh
wasmtk wasic hello-world.ts
wasmtk run hello-world.wasm
hello world
```

Use `wasmtk info` to inspect the exported functions and metadata of any compiled binary:

```sh
wasmtk info hello-world.wasm
```

## Project Structure

```text
BasicsOfCodingWASMWithwasmtk/
├── upstream/
│   └── basicsofcodinggo/  — reference implementation (git submodule)
└── ##_topic-name/
    ├── topic-name.ts      — TypeScript source (compiled to WASM via wasmtk wasic)
    └── topic-name.md      — run command and expected output
```

Lessons are numbered with a two-digit prefix matching BasicsOfCodingGo exactly: same lesson numbers, same folder names.

## Lessons

| # | Topic |
|---|-------|
| 01 | hello-world |
| 02 | values |
| 03 | variables |
| 04 | constants |
| 05 | for |
| 06 | if-else |
| 07 | switch |
| 08 | arrays |
| 09 | slices |
| 10 | maps |
| 11 | range |
| 12 | functions |
| 13 | multiple-return-values |
| 14 | variadic-functions |
| 15 | closures |
| 16 | recursion |
| 17 | pointers |
| 18 | structs |
| 19 | methods |
| 20 | interfaces |
| 21 | errors |
| 22 | strings-and-runes |
| 23 | struct-embedding |
| 24 | enums |
| 25 | custom-errors |
| 26 | generics |
| 27 | goroutines |
| 28 | channels |
| 29 | select |
| 30 | timeouts |
| 31 | timers |
| 32 | tickers |
| 33 | mutexes |
| 34 | atomic-counters |
| 35 | waitgroups |
| 36 | worker-pools |
| 37 | rate-limiting |
| 38 | recover |
| 39 | logging |
| 40 | sorting |
| 41 | sorting-by-functions |
| 42 | panic |
| 43 | defer |
| 44 | collection-functions |
| 45 | string-functions |
| 46 | string-formatting |
| 47 | regular-expressions |
| 48 | json |
| 49 | xml |
| 50 | time |
| 51 | epoch |
| 52 | time-formatting-parsing |
| 53 | random-numbers |
| 54 | number-parsing |
| 55 | url-parsing |
| 56 | sha1-hashes |
| 57 | base64-encoding |
| 58 | reading-files |
| 59 | writing-files |
| 60 | line-filters |
| 61 | file-paths |
| 62 | directories |
| 63 | temporary-files-and-directories |
| 64 | command-line-arguments |
| 65 | command-line-flags |
| 66 | command-line-subcommands |
| 67 | environment-variables |
| 68 | testing-and-benchmarking |
| 69 | http-client |
| 70 | http-server |
| 71 | context |
| 72 | tcp-server |
| 73 | text-templates |
| 74 | execing-processes |
| 75 | spawning-processes |
| 76 | signals |
| 77 | exit |
| 78 | sha256-hashes |

## WASM and TypeScript Constraints

These examples use the `wasic` compilation path in wasmtk, which compiles a specific subset of TypeScript to a standalone WASI module. Some features common in standard TypeScript or Node.js are not available in this environment.

**Not supported:**

- `for...of` / `for...in` — examples use indexed `for` loops
- Classes — examples use `interface` + factory functions
- `Math.random()` — examples use a seeded deterministic PRNG (mulberry32, seed 42)
- `Date` object — time/epoch lessons use static example values
- `JSON.parse()` / `JSON.stringify()` — built and parsed manually
- `parseInt()` / `parseFloat()` — implemented manually or via typed conversion
- Network APIs (`fetch`, HTTP, TCP) — not available in WASI
- Process APIs (`exec`, `spawn`, signals) — not available in WASI
- Custom exit codes — `proc_exit` always exits 0

**Workarounds used in specific lessons:**

- Concurrency (27–37): WebAssembly is single-threaded; sequential equivalents with explanatory notes
- Networking (69–72): No network stack in WASI; hardcoded simulations with explanatory notes
- File I/O (58–60): Hardcoded simulations; file read/write and stdin are not available in WASI
- Command-line arguments and flags (64–66): Hardcoded demo values with explanatory notes
- Cryptography (78): SHA-256 pre-computed; no crypto API in WASI

Each lesson `.md` file notes any WASM-specific workarounds at the top.

## Attribution

This project is adapted in part from **[Basics of Coding Go](https://github.com/jrmarcum/BasicsOfCodingGo)**
by [Jon Marcum](https://github.com/jrmarcum), which was itself adapted from
**[Go by Example](https://github.com/mmcgrana/gobyexample)**
by [Mark McGranaghan](https://github.com/mmcgrana), both licensed under the
[Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/).

The lesson files and code examples derived from those works retain their
CC BY 3.0 license. This project exists as a platform for multi-language
comparative study of syntax, language simplicity, lines of code required,
and runtime performance.

## License

This repository contains two tiers of content:

| Content | License |
| --- | --- |
| Lesson files and code examples adapted from *Basics of Coding Go* / *Go by Example* | [CC BY 3.0](http://creativecommons.org/licenses/by/3.0/) — see NOTICE |
| Original contributions by Jon Marcum (project structure, README, comparative study additions) | [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — see LICENSE |

The root `LICENSE` file (CC0) applies to Jon Marcum's original contributions.
The `NOTICE` file clarifies that CC BY 3.0 governs all content adapted from *Go by Example* and *Basics of Coding Go*.
