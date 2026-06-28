# quickreplace

A small command line tool written in Rust that finds and replaces text in a
file. It reads an input file, swaps every match of a pattern with new text, and
writes the result to an output file.

## What it does

You give it a pattern to search for, the text to replace it with, an input
file, and an output file. The tool reads the input, replaces every match, and
saves the result. The input file is left unchanged.

The search pattern is a regular expression, so you can match simple words or
more complex patterns.

## Usage

```bash
quickreplace <target> <replacement> <INPUT> <OUTPUT>
```

- `target`: the pattern to search for (a regular expression)
- `replacement`: the text to put in its place
- `INPUT`: path to the file to read
- `OUTPUT`: path to the file where the result is written

### Example

Replace every "cat" with "dog" in `notes.txt` and save to `out.txt`:

```bash
quickreplace cat dog notes.txt out.txt
```

## How it works

1. It reads the four arguments from the command line. If the count is wrong, it
   prints how to use the tool and stops.
2. It reads the whole input file into memory.
3. It builds a regular expression from the target and replaces every match.
4. It writes the new text to the output file.

If any step fails, for example the file is missing or the pattern is not valid,
it prints a clear error in red and exits.

## Project layout

```
quickreplace/
  src/main.rs    the program code
  Cargo.toml     project settings and dependencies
```

## Build

You need Rust installed.

```bash
cargo build --release
```

The built program is placed at `target/release/quickreplace`.

## Dependencies

- `regex` for pattern matching and replacement
- `text-colorizer` for colored error messages
