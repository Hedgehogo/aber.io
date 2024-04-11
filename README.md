# Description
Aber is a high-level programming language inspired by languages such as Rust, Lisp, Elixir, and Zig. It includes high-level abstractions such as structures, unions and traits, compile-time computation and automatic generalization. But it also allows low-level memory access and platform-dependent code writing. 

# Syntax
"Character" refers to Unicode grapheme cluster.

## Whitespace
` `, ⇥ (Tab) and ↵ (Newline) are considered whitespace characters. Whitespace can be empty.

## Comments
The comment begins with `//` and ends at the end of the line.

Example:
```rs
// At the beginning of the line
```

## Literals
### Numbers
Digits (`0` - `9`) and capital letters of the English alphabet (`A` - `Z`) can be used, if they exist in the required number system. `_` can be used as a separator between digits. Signed numbers can begin with `-`. The default numbering system is decimal. 

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

### Strings

**String**

It is written in `"`. Characters are escaped with `\`. The characters supported for escaping: 
| The symbol after `\` | The result   |
|----------------------|--------------|
| `"`                  | `"`          |
| `#`                  | `#`          |
| `\`                  | `\`          |
| `n`                  | ↵ (Newline)  |
| `t`                  | ⇥ (Tab)      |
| ↵ (Newline)          | (Nothing)    |

Any characters are allowed, except `"` without `\` before it, including ↵ (Newline).

Examples:
```kotlin
"Hello\t\n\"Aber\"!" // Hello	
                     // "Aber"!
```
```kotlin
"Hello\t
\"Aber\"!" // Same as the first one
```
```kotlin
"Hello\t\
\n\"Aber\"!" // Same as the first one
```

**Raw string**
Starts with a non-zero n number of `"` characters and a `#` character at the end. ends with `#` and n `"` characters.

Examples:
```dart
"#Hello	
"Aber"!#" // Same as in normal strings
```
```kotlin
"""#	""Aber#""" // "\t\"\"Aber"
```
```kotlin
 """Aber"""  // "" "Aber" ""
"""#Aber#""" // "Aber"
```

## Expression
An expression is a set of syntactic units separated by whitespace.

Examples:
```rs

```
```rs
"hello"
```
```rs
10 "hello" 15.4
```

## Pair
The pair is denoted by `:`. It captures one syntactic unit on the left.

Example:
```rs
"count": 
```

## Tuple
Tuples start with `(` and end with `)`, elements within are separated by `,`. A comma before a closing bracket is optional.

Examples:
```rs
() 
```
```rs
(10)
```
```rs
(42, )
```
```rs
(5, "hello")
```

## Block
Blocks start with `{` and end with `}`, expressions within are separated by `;`. A semicolon before a closing bracket creates an empty expression at the end of the block.

Examples:
```rs
{}
```
```rs
{10}
```
```rs
{42; }
```
```rs
{5; "hello"}
```

## Explicit generic parameters
Explicit generic parameters start with `[` and end with `]`, parameters within are separated by `,`. A comma before a closing bracket is optional.

Examples:
```rs
[]
```
```rs
[10]
```
```rs
[42, ]
```
```rs
[5, Type]
```

## Сall
Any non-zero character set, that does not start with digit (`0` - `9`) or `-` with one digit and does not include `.`, `,`, `;`, `:`, `'`, `"`, `=`, `@`, `/`, `(`, `)`, `{`, `}`, `[`, `]` and whitespace, is considered a call.

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

## Method call
A method call is indicated by `.` followed by a call. It captures the largest expression on the left.

Examples:
```
foo.foo
```
```
bar 10.foo+bar
```
```
baz(10, "hello").baz0-foo*$%
```

## Сhild сall
A сhild call is indicated by `::` followed by a call. It captures the largest expression on the left.

Examples:
```
foo::foo
```
```
bar 10::foo+bar
```
```
baz(10, "hello")::baz0-foo*$%
```

## Negative call
The negative call is denoted by `@`. It captures the largest expression on the right. It has higher precedence than a method call or a child call.

Examples:
```
@foo
```
```
@foo.foo
```
```
@foo::foo
```

## Assignment
The assignment is denoted by `=`. It captures the largest expression to the right and left. It has higher priority than a method call, a child call, or a negative call.

Examples:
```
a = foo
```
```
a = foo.foo
```
```
@bar = foo::foo
```
