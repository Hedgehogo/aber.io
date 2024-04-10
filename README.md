# Description
Aber is a high-level programming language inspired by languages such as Rust, Lisp, Elixir, and Zig. It includes high-level abstractions such as structures, unions and traits, compile-time computation and automatic generalization. But it also allows low-level memory access and platform-dependent code writing. 

# Syntax
"A character" refers to Unicode grapheme cluster.

## Whitespace
` `, ⇥ (Tab) and ↵ (Newline) are considered whitespace characters.

## Comments

The comment begins with `//` and ends at the end of the line.

Example:
```rs
// At the beginning of the line
```

## Literals
### Numbers
Digits (0-9) and capital letters of the English alphabet (A-Z) can be used, if they exist in the required number system. `_` can be used as a separator between digits. Signed numbers can begin with `-`. The default numbering system is decimal. 

**Integer numbers**

Example:
```rs
3_005 // 3005 in decimal
```

**Floating point numbers**

`.` is used as a separator between the integer part and the fractional part. The integer part is required to have at least one digit.

Examples:
```rs
1.15
```
```rs
23.
```
```rs
.1 // Error
```

The functional further works for any numbers. 

**Specifying the number system.**

Before the number is written the number system in decimal notation, and then it is written `'`.

Examples:
```rs
16'FF // Hexadecimal, integer, 255 in decimal
```
```rs
2'01100101 // Binary, integer, 101 in decimal
```
```rs
3'0.1 // Trinary, floating point, 1/3 in decimal
```
```rs
2'10. // Binary, floating point, 2 in decimal
```

## Function call
Any non-zero character set other than whitespace and `.`, `,`, `;`, `:`, `'`, `"`, `=`, `/`, `(`, `)`, `{`, `}`, `[`, `]` are considered function calls. Also not beginning with `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9` or with the same character set preceded by `-`.

Examples:
```
foo
```
```
foo+bar
```
```
baz0-foo*$%
```
