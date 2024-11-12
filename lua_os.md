# The `os` Library

The `os` library functions can be called with `os.function_name()` syntax.

## Table of Contents

- [The `os` Library](#the-os-library)
  - [Date and Time Functions](#date-and-time-functions)
    - [`os.time`](#ostime)
    - [`os.date`](#osdate)
    - [`os.difftime`](#osdifftime)
  - [System Command Execution](#system-command-execution)
    - [`os.execute`](#osexecute)
  - [Environment Variables](#environment-variables)
    - [`os.getenv`](#osgetenv)
  - [File Management Functions](#file-management-functions)
    - [`os.rename`](#osrename)
    - [`os.remove`](#osremove)
  - [Miscellaneous Functions](#miscellaneous-functions)
    - [`os.clock`](#osclock)
    - [`os.exit`](#osexit)

## Date and Time Functions

### `os.time`

The `os.time` function returns the current time as the number of seconds since the Unix epoch (January 1, 1970). This can be used for timestamping or measuring elapsed time.

```lua
local currentTime = os.time()
print("Current time:", currentTime)
```

You can also pass a table to `os.time` to get a specific timestamp.

```lua
local customTime = os.time{year=2023, month=12, day=31, hour=23, min=59, sec=59}
print("Custom time:", customTime)
```

### `os.date`

The `os.date` function formats the current time or a given timestamp. By default, `os.date` returns a readable date string, but you can specify a format.

```lua
print(os.date())  -- Output: Wed Nov 10 12:30:00 2024
print(os.date("%Y-%m-%d %H:%M:%S"))  -- Output: 2024-11-10 12:30:00
```

Common format specifiers:

- `%Y`: Year
- `%m`: Month (01-12)
- `%d`: Day of the month (01-31)
- `%H`: Hour (24-hour format)
- `%M`: Minute (00-59)
- `%S`: Second (00-59)

### `os.difftime`

`os.difftime` calculates the difference in seconds between two timestamps, useful for measuring time intervals.

```lua
local start = os.time()
-- Some processing
local finish = os.time()
print("Elapsed time:", os.difftime(finish, start), "seconds")
```

## System Command Execution

### os.execute

`os.execute` runs a shell command from within Lua. This is useful for executing system commands directly.

```lua
os.execute("mkdir new_folder")  -- Creates a directory named "new_folder"
```

> **_IMPORTANT NOTE:_**  Use with caution, as executing shell commands can have security implications.

## Environment Variables

### os.getenv

`os.getenv` retrieves the value of an environment variable, which can be useful for accessing system configuration information.

```lua
local path = os.getenv("PATH")
print("System PATH:", path)
```

## File Management Functions

### os.rename

The `os.rename` function renames or moves a file or directory. It takes two arguments: the current path and the new path.

```lua
os.rename("old_name.txt", "new_name.txt")  -- Renames old_name.txt to new_name.txt
```

### os.remove

The `os.remove` function deletes a specified file. It only works on files, not directories.

```lua
os.remove("unnecessary_file.txt")  -- Deletes unnecessary_file.txt
```

## Miscellaneous Functions

### os.clock

`os.clock` returns the CPU time (in seconds) used by the program since it started. This is useful for benchmarking code execution time.

```lua
local start = os.clock()
-- Code to measure
local finish = os.clock()
print("CPU time:", finish - start, "seconds")
```

### os.exit

`os.exit` terminates the Lua script. It can take an optional status code: `0` for a normal exit, or a non-zero value to indicate an error.

```lua
print("Goodbye!")
os.exit()
```

