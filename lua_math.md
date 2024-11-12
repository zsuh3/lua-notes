# The `math` Library

The `math` library functions can be called with `math.function_name()` syntax.

## Table of Contents

- [The `math` Library](#the-math-library)
  - [Constants](#constants)
  - [Common Functions](#common-functions)
    - [Rounding Functions](#rounding-functions)
    - [Exponential and Logarithmic Functions](#exponential-and-logarithmic-functions)
    - [Trigonometric Functions](#trigonometric-functions)
    - [Random Numberes](#random-numbers)
    - [Power and Modulus](#power-and-modulus)

## Constants
- `math.pi`: Returns the value of pi (approximately 3.14159).
- `math.huge`: Represents infinity (`∞`), useful for comparisons.

## Common Functions

### Rounding Functions

- `math.floor(x)`: Rounds `x` down to the nearest integer.
- `math.ceil(x)`: Rounds `x` up to the nearest integer.
- `math.abs(x)`: Returns the absolute value of `x`.

### Exponential and Logarithmic Functions

- `math.sqrt(x)`: Returns the square root of `x`.
- `math.exp(x)`: Returns `e` raised to the power of `x` (`e^x`).
- `math.log(x [, base])`: Returns the logarithm of `x` with the specified `base` (default is natural log).

### Trigonometric Functions

All trigonometric functions in Lua work with angles in radians.

- `math.sin(x)`: Sine of `x` (in radians).
- `math.cos(x)`: Cosine of `x` (in radians).
- `math.tan(x)`: Tangent of `x` (in radians).
- `math.asin(x)`, `math.acos(x)`, `math.atan(x)`: Inverse sine, cosine, and tangent.

### Random Numbers

- `math.random()`: Returns a random floating-point number between `0` and `1`.
- `math.random(n)`: Returns a random integer between `1` and `n`.
- `math.random(min, max)`: Returns a random integer between `min` and `max`.
- `math.randomseed(seed)`: Sets the seed for random number generation, ensuring reproducibility.

```lua
math.randomseed(os.time())  -- initialise random seed
```

### Power and Modulus

- `math.pow(x, y)`: Raises `x` to the power of `y`.
- `math.fmod(x, y)`: Returns the remainder of `x / y` (floating-point modulus).

