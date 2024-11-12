# The `io` Library

The `io` library functions can be called with `io.function_name()` syntax.

## Table of Contents

- [The `io` Library](#the-io-library)
  - [User Input](#user-input)
    - [`io.read`](#ioread)
      - [Input Formats](#input-formats)
    - [`io.write`](#iowrite)
      - [Formatting](#formatting)
  - [Working with Files](#working-with-files)
    - [`io.input`](#ioinput)
    - [`io.output`](#iooutput)
    - [`io.open` and `io.close`](#ioopen-and-ioclose)
    - [`io.read` and `io.write`](#ioread-and-iowrite)
    - [File Position](#file-position)

## User Input

### `io.read`

`io.read` reads input from the user.

```lua
local variable = io.read("*format")
```

#### Input Formats

- `"*n"`: Reads a number.
- `"*l"`: Reads a line (up to the newline character).
- `"*a"`: Reads the entire input (until end-of-file).
- `"*s"`: Reads a string (skipping any leading whitespace).

### `io.write`

`io.write` in Lua is used to output text to the console.

```lua
io.write(value1, value2, ...)
```

#### Formatting

- `\n`: Newline
- `\t`: Tab
- `\\`: Backslash
- `\"`: Double quote

## Working with Files

### `io.input`

`io.input` can be used to set the default input file or get the current input file handle.

```lua
io.input("input.txt")  -- Sets "input.txt" as the default input file
local content = io.read("*a")  -- Reads the entire file
print(content)
```

If a file is specified, `io.input` opens it for reading and sets it as the default input file. You can then use `io.read` to read from this file without specifying a file handle.

To reset `io.input` to standard input, use:

```lua
io.input(io.stdin)
```

### `io.output`

`io.output` sets or gets the default output file.

```lua
io.output("output.txt")  -- Sets "output.txt" as the default output file
io.write("Hello, file!")  -- Writes to "output.txt"
```

To reset `io.output` to standard output, use:

```lua
io.output(io.stdout)
```

### `io.open` and `io.close`

- The `io.open` function opens a file in a specified mode and returns a file handle.
- Close the file with `file:close()` once operations are complete to ensure any buffered data is written and system resources are freed.

```lua
local file = io.open("example.txt", "mode")
-- Do something with the file (read, write or append)
file:close()
```

| Mode | Description |
| --- | --- |
| "r" | Read mode |
| "w" | Write mode (overwrites) |
| "a" | Append mode |
| "r+" | Read/update mode |
| "w+" | Write/update mode (overwrites) |
| "a+" | Append/update mode |

### `io.read` and `io.write`

- [`io.read`](#ioread)
- [`io.write`](#iowrite)

### File Position

Lua provides methods for seeking and controlling the file pointer’s position with `file:seek`.

- `file:seek("set", position)` moves to the specified position.

```lua
file:seek("set", 0)  -- Moves to the start of the file
file:seek("end")     -- Moves to the end of the file
```

Modes:

- `"set"`: Start of the file.
- `"cur"`: Current position.
- `"end"`: End of the file.

