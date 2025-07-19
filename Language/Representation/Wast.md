A *Weak Abstract Syntax Tree* (*WAST*) is a structure consisting of nodes, each of which describes a different syntactic unit. A tree is called weak because an expression is simply a sequence at this level, although most languages define it in a more structured way at the syntax level.

## Terminology used
An *expression* is a sequence of nodes.

A *statement* contains an *expression* or an *assignment*.

An assignment contains 2 *expressions*.

An *identifier* is a sequence of grapheme clusters satisfying the requirements of the *identifier syntax*. 

A *list of generic arguments* contain a sequence of *expressions*.

## Existing nodes and their contents

| Node             | Node contents                                                                                                                                                                           |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *Number*         | A base of a number system, a sequence of digits in that system that represents the integer part, and an optional sequence of digits in that system that represents the fractional part. |
| *Char*           | A single Unicode grapheme cluster.                                                                                                                                                      |
| *String*         | A sequence of Unicode grapheme clusters.                                                                                                                                                |
| *Pair*           | One other node.                                                                                                                                                                         |
| *Tuple*          | A sequence of *expressions*.                                                                                                                                                            |
| *Block*          | A sequence of *statements* and one *expression*.                                                                                                                                        |
| *Call*           | An *identifier* and a *list of generic arguments*.                                                                                                                                      |
| *Method call*    | An *expression* and a *call* node.                                                                                                                                                      |
| *Child call*     | An *expression* and a *call* node.                                                                                                                                                      |
| *Negative call*  | An expression.                                                                                                                                                                          |
| *Initialization* | An *expression* and a sequence of *expressions*                                                                                                                                         |
