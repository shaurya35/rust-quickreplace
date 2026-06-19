# quickreplace

A small Rust command line tool that replaces all occurrences of one string with another in a text file.

## Usage

```
quickreplace <target> <replacement> <INPUT> <OUTPUT>
```

- `target`: the string to search for
- `replacement`: the string to replace it with
- `INPUT`: path to the input file
- `OUTPUT`: path to the file where the result is written

## Build

```
cargo build --release
```
