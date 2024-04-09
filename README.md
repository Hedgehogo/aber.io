# Description
Aber is a high-level programming language inspired by languages such as Rust, Lisp, Elexir, and Zig. It includes high-level abstractions such as structures, unions and traits, compile-time computation and automatic generalization. But it also allows low-level memory access and platform-dependent code writing. 

# Syntax
The character is referred to as the Unicode grapheme cluster.

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
3'0.1 // Trinary, real, 1/3 in decimal
```
```rs
2'10. // Binary, real, 2 in decimal
```

**Scientific notation.**

A number can be followed by an `e` followed by a full *integer number* (can be written in different number systems, etc.). This number is an exponent.

Examples:
```rs
1e16'F // 1 * (10^15) in decimal
```
```rs
9.109_383_56e−31 // 9.10938356 * (10^−31) in decimal
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
