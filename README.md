# Lua Introduction

<img src="./lua_logo.svg" width=200>

## Table of Contents

- [Welcome to Lua](#welcome-to-lua)
  - [Lua Introduction](#lua-introduction)
  - [What can I do with Lua?](#what-can-i-do-with-lua)
  - [Comments](#comments)
  - [Printing](#printing)
  - [Data Types](#data-types)
  - [Strings](#strings)
    - [Multi-line Strings](#multi-line-strings)
    - [Type Conversion](#type-conversion)
    - [String Operations](#string-operations)
      - [String Length](#string-length)
      - [Case Conversion](#case-conversion)
      - [ASCII Conversion](#ascii-conversion)
      - [Substrings](#substring)
      - [Finding Substrings](#finding-substrings)
      - [Pattern Matching](#pattern-matching)
      - [Substitution](#substitution)
      - [Repitition](#repitition)
      - [Formatting](#formatting)
  - [Operations](#operations)
    - [Arithmetic](#arithmetic)
    - [Relational](#relational)
    - [Lexical - Comparisons](#lexical---comparisons)
  - [`if` Statements](#if-statements)
    - [`if-else` Statements](#if-else-statements)
    - [`if-elseif-else` Statements](#if-elseif-else-statements)
  - [Loops](#loops)
    - [`while` Loop](#while-loop)
    - [`repeat-until` Loop](#repeat-until-loop)
    - [Numeric `for` Loop](#numeric-for-loop)
    - [Generic `for` Loop](#generic-for-loop)
  - [Tables](#tables)
    - [Accessing Tables](#accessing-tables)
    - [Modifying Tables](#modifying-tables)
    - [Iterative Over Tables](#iterating-over-tables)
    - [Table Functions](#table-functions)
    - [Tables as Objects](#tables-as-objects)
  - [Functions](#functions)
    - [Local Functions](#local-functions)
    - [Anonymous Functions](#anonymous-functions)
  - [Co-Routines](#co-routines)
    - [Creating Co-Routines](#creating-co-routines)
    - [Running Co-Routines](#running-co-routines)
    - [Suspending Co-Routines](#suspending-co-routines)
    - [Co-Routine Status](#co-routine-status)

## Lua Introduction

Lua is a procedural programming language used to develop software, work with machine learning and create all sorts of games, from a basic text game all the way to VR games.

## What can I do with Lua?

Lua is quite a versatile programming language. But, it's mostly best at things like:

| Use Case | Description | Examples |
| --- | --- | --- |
| Embedded programming | Writing code to run on IoT or small computing devices | Raspberry Pi |
| Video game programming | Writing video game logic | ROBLOX, PICO-8, LOVE2D, Defold |
| Network programming | Writing fast and small programs for computer networking | CISCO Systems, nmap, Kong API Gateway, ModSecurity |
| Cross-language libraries | Writing flexible and interoperable libraries that can work with multiple programming languages | NLua (.NET / C#) |
| Complex config files | Writing configuration files that require lots of complexity and advanced features | Neovim config |

## Commenting

```lua
-- single line comments
```

```lua
--[[
multi-line comments
]]
```

## Printing

In Lua, comments can be either single quotes or double quotes.

```lua
print("Hello World!")
print('Hello World!')
```

Using commas will add a (tab) space between each string.

```lua
print("Hello", "World!")
-- Output: Hello	World!
```

Using `..` (concatenation operator) will combine the two strings into one.

```lua
print("Hello " .. "World!")
-- Output: Hello World!
```

## Data Types

There are 5 fundamental types of data in Lua:

| Type | Example | Description |
| --- | --- | --- |
| string | `Hello` | Text data, enclosed in single or double quotes |
| number | `123`, `4.56`, `-789` | Contains either an integer or a decimal number, as well as positive or negative signs |
| boolean | `true`, `false` | True or False |
| nil | `nil` | Represents the absence of a value, often known as `null` in other languages |
 table | `{key1 = value1, key2 = value2, ...}` <br> or `{value1, value2, ...}` | Contains a collection of related values, accessible by their key or by their position in the list |

A **variable** in computer programming is used to store information inside a computer program. Each value that you can give to a variable has a **data type**, which is a term that describes what type of data is stored into a variable.

Lua is a _dynamically typed_ programming language, meaning you don't need to explicitly say what type of data a variable should contain and the Lua interpreter will figure out the type for you.

By default, variables are **global** in Lua, which means they can be accessed anywhere in the script. To restrict a variable's scope to the current block or function, use the local keyword.

```lua
local message = "Hello"
```

## Strings

### Multi-line Strings

Lua supports multi-line strings using double square brackets `[[ ]]` or a custom delimiter with `=[[]]=` to handle nested brackets.

```lua
message = [[
This is a
multi-line
string.
]]
```

Using `[=[` and `]=]` allows including `[[` and `]]` within the string, which is useful if the string contains Lua's default bracket delimiters.

```lua
message = [=[
Here is a string with nested brackets:
[[ Nested Content ]]
]=]
```
### Type Conversion

```lua
type(str)            -- Output: "string"
type(tonumber(str))  -- Converts str to number if possible; returns "nil" if not
type(tostring(str))  -- Converts any data type to string; output: "string"
```

### String Operations

#### String Length

`#str` and `string.len(str)` both return the length of `str`.

```lua
print(#str)
print(string.len(str))
```

#### Case Conversion

- `string.lower` converts to lowercase.
- `string.upper` converts to uppercase.

#### ASCII Conversion

- `string.char` converts an ASCII code to a character.
- `string.byte` converts a character to its ASCII code.

#### Substring

- `string.sub(str, start, end)` extracts a substring from the start to the end position.

```lua
local str = "Hello World!"
print(string.sub(str, 1, 5))
-- Output: "Hello"
```

#### Finding Substrings

- `string.find` returns the starting and ending indices of the first occurrence of a substring.

```lua
local beginning, ending = string.find(str, "orl")
print(beginning, ending)
-- Output: 8	10
```

#### Pattern Matching

- `string.match` searches for a pattern and returns the matched part of the string.

#### Substitution

- `string.gsub(str, "old", "new")` replaces all occurrences of "old" with "new".

#### Repitition

```lua
print(string.rep("Lua", 3))
-- Output: "LuaLuaLua"
```

#### Formatting

```lua
print(string.format("Pi: %.2f\nAge: %i", math.pi, 21))
-- Output:
-- Pi: 3.14
-- Age: 21
```

## Operations

### Arithmetic

Lua's arithmetic operators follow the standard set found in most other programming languages:

| Operation | Symbol |
| --- | --- |
| Add | `+` |
| Subtract | `-` |
| Multiply | `*` |
| Divide | `/` |
| Exponents | `^` |
| Modulus | `%` |
| Unary negation | `-` |

### Relational

Relational operators allow comparison between two values. They return a boolean result (true or false).

| Equator | Symbol |
| --- | --- |
| Equal to | `==` |
| Not equal to | `~=` |
| Greater than | `>` |
| Greater than or equal to | `>=` |
| Less than | `<` |
| Less than or equal to | `<=` |

### Lexical - Comparisons

The word _lexical_ means something that relates to the vocabulary of a language. In the case of programming, it typically refers to a written word that has a meaning in the program.

The following words function as _operators_ in Lua:

- `and`
- `or`
- `not`

## `if` Statements

```lua
if condition then
  -- code to execute if condition is true
end
```

### `if-else` Statements

```lua
if condition then
  -- code to execute if condition is true
else
  -- code to execute if condition is false
end
```

### `if-elseif-else` Statements

```lua
if condition1 then
  -- code to execute if condition1 is true
elseif condition2 then
  -- code to execute if condition2 is true
else
  -- code to execute if condition is false
end
```

## Loops

### `while` Loop

```lua
while condition do
  -- code to execute while the condition is true
end
```

### `repeat-until` Loop

```lua
repeat
  -- code to execute
until condition
```

### Numeric `for` Loop

```lua
for variable = start, stop, step do
  -- code to execute in each iteration
end
```

### Generic `for` Loop

```lua
for key, value in pairs(table) do
  -- code to execute for each key-value pair
end
```

- `pairs` iterates over all key-value pairs in a table.

```lua
local fruits = {apple = "red", banana = "yellow", grape = "purple"}
for fruit, color in pairs(fruits) do
    print(fruit, color)
end
-- Output:
-- apple red
-- banana yellow
-- grape purple
```

- For arrays, you can use `ipairs`, which iterates in numeric order by index.

```lua
local numbers = {10, 20, 30}
for index, value in ipairs(numbers) do
    print(index, value)
end
-- Output:
-- 1 10
-- 2 20
-- 3 30
```

## Tables

In Lua, tables are the only data structure, acting as arrays, dictionaries, or objects. Tables are created with `{}` and can store any type of data.

```lua
local myTable = {}
```

Array Style Table (Indexed by Numbers):

```lua
local array = {10, 20, 30}
```

Table with Key-Value Pairs:

```lua
local person = {
    name = "Alice",
    age = 30,
    occupation = "Engineer"
}
```

### Accessing Tables

- **Dot Notation**: For keys that are valid identifiers (like `name`), you can use `.` to access values.
- **Bracket Notation**: Use `[]` for keys that are numbers or strings with spaces/special characters.

```lua
print(person.name)           -- Output: Alice
print(person["occupation"])  -- Output: Engineer
print(array[1])              -- Output: 10
```

### Modifying Tables

```lua
person.age = 31              -- Update existing key
person["city"] = "New York"  -- Add new key-value pair
person.age = nil             -- Delete a key by setting it to nil
```

### Iterating Over Tables

- Use `pairs()` to iterate over all key-value pairs in a table. This is especially useful for dictionary-style tables.
- Use `ipairs()` for array-style tables (numerically indexed) to iterate in order of indices.

### Table Functions

Lua provides several useful functions for working with tables. Some of these are available via the table library.

- `table.concat(table, separator, start, end)`: Joins elements of an array-style table into a single string, optionally inserting a separator between elements and allowing a specified range with `start` and `end` indices.

- `table.insert(t, value)`: Adds `value` to the end of table `t`.

- `table.remove(t, index)`: Removes the element at `index` in table `t`.

- `#t` (Length Operator): Returns the number of elements in an array-style table.

### Tables as Objects

```lua
local car = {
    make = "Toyota",
    model = "Corolla",
    honk = function()
        print("Honk!")
    end
}

car.honk()
-- Output: Honk!
```

## Functions

Functions in Lua are blocks of reusable code designed to perform specific tasks. They can take parameters, return values, and are defined with the `function` keyword.

```lua
function functionName(parameters)
  -- function body
end
```

### Local Functions

- By default, functions in Lua are global, but you can make them local by using the `local` keyword. Local functions are only accessible within the scope where they’re defined.

```lua
local function functionName(parameters)
  -- function body
end
```

### Anonymous Functions

- Lua supports anonymous (or lambda) functions, which are functions without a name.

```lua
local add = function(a, b)
    return a + b
end

print(add(2, 3))
-- Output: 5
```

## Co-Routines

Coroutines are Lua's way of handling concurrency. They allow multiple functions to run independently, pausing and resuming as needed. Unlike threads, coroutines share the same thread of execution, meaning they don’t run in parallel but can yield control back and forth.

### Creating Co-Routines

Coroutines in Lua are created with `coroutine.create`, which takes a function as an argument and returns a coroutine object.

```lua
local co = coroutine.create(function()
    print("Hello from coroutine!")
end)
```

### Running Co-Routines

To start or resume a coroutine, use `coroutine.resume`. This function starts the coroutine if it’s in the “suspended” state, making it run until it either completes or calls `coroutine.yield`.

```lua
coroutine.resume(co)
-- Output: Hello from coroutine!
```

### Suspending Co-Routines

Coroutines can pause their execution with `coroutine.yield`. This function suspends the coroutine and returns control to where `coroutine.resume` was called. When resumed, the coroutine continues from where it yielded.

```lua
local co = coroutine.create(function()
    for i = 1, 3 do
        print("Coroutine iteration:", i)
        coroutine.yield()
    end
end)

coroutine.resume(co)  -- Output: Coroutine iteration: 1
coroutine.resume(co)  -- Output: Coroutine iteration: 2
coroutine.resume(co)  -- Output: Coroutine iteration: 3
```

### Co-Routine Status

Use `coroutine.status(co)` to check the status of a coroutine:

- "**suspended**": Coroutine is paused and can be resumed.
- "**running**": Coroutine is currently running.
- "**normal**": Coroutine is active but paused due to another coroutine.
- "**dead**": Coroutine has finished executing.

