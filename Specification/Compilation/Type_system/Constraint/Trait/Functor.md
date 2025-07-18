A *functor* is an [*object*](./../../Object/_.md) whose [*type*](./../Type/_.md) implements the [*trait*](./_.md) `std::core::trait::Call`.

Referring to a *functor* is treated as a *call*. The *call* is divided into *arguments* and *return value*. 

Each *argument* is an [*object*](./../../Object/_.md). For one [*type*](./../Type/_.md) of *functor*, the number, order and [*types*](./../Type/_.md) of *arguments* are fixed. The *return value* is an [*object*](./../../Object/_.md). For each [*type*](./../Type/_.md) of *functor* the [*type*](./../Type/_.md) of *return value* is fixed.

Syntactically, a *call* must be followed by its *arguments*, separated by [*whitespace syntax*](./../../../Order/Syntax/_.md#whitespace). Then the whole construct together will be considered a *return value*. If the *argument* is a *functor*, it captures its *arguments* earlier. *Arguments* are computed in the order in which they are passed.

Example:
> Suppose we already have a *functor* that can be accessed by writing `max`.
> Also assume that its *arguments* can be *number literals*, and its *return value* can be a number.
> 
> Then the given expression: 
> ```aber
> max 10 15
> ```
> can be considered as:
> ```aber
> 15
> ```