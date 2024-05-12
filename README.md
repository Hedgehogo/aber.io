# Description
Aber is a high-level programming language inspired by languages such as Rust, Lisp, Elixir, and Zig. It includes high-level abstractions such as structures, unions and traits, compile-time computation and automatic generalization. But it also allows low-level memory access and platform-dependent code writing.
# Examples

**Hello World**

Contents of the file `hello_world.aber`:
```aber
std::use_prelude;

print run() "Hello World!" ();
```
Сompiler command:
```
aberc --script hello_world.aber
```
Output:
```
Hello World!
```

**Fibonacci**

Contents of the file `fibonacci.aber`:
```aber
std::use_prelude;

fn fibonacci(n) {
	if n.< 2 {
		return n;
	}
	fibonacci(n.- 1).+ fibonacci(n.- 2)
};

print "result: {}" (run fibonacci(9));
```
Сompiler command:
```
aberc --script fibonacci.aber
```
Output:
```
result: 21
```

**Structures and unions**

Contents of the file `structures_unions.aber`:
```aber
std::use_prelude;

struct Vec2[T](x: T, y: T);

impl Vec2 {
	fn new(x, y) {
		Self::constuct(x, y)
	}
}

union Option(None(), Some(_));

let vec2(run Vec2::new(10, 15));
println "x: {}, y: {}" (vec2.x, vec2.y);

let option(Option::Some(23));
option.match(
	Option::Some(i): println "Some({})" (i)
);
```
Сompiler command:
```
aberc --script structures_unions.aber
```
Output:
```
x: 10, y: 15
Some(23)
```

**Traits**

Contents of the file `traits.aber`:
```aber
std::use_prelude;
use std::(derive, std::fmt::Debug, std::ops::Operator);

struct Vec2[T](x: T, y: T);

derive(Vec2, Debug);

impl Vec2 {
	fn new(x, y) {
		Self::constuct(x, y)
	}
}

impl(T) Operator(+)[Vec2[T]]: Vec2[T]
where (
	T: Operator(+)[T]
) {
	fn Output() { Vec2[T::Output] }

	fn +(self: Self, other: Self) {
		Self::new(self.x.+ other.x, self.y.+ other.y) 
	}
}

println "result: {:?}" (run { Vec2::new(10, 15).+ Vec2::new(42, 31) });
```
Сompiler command:
```
aberc --script traits.aber
```
Output:
```
result: Vec2{ x: 52, y: 46 }
```

**Unit testing**

Contents of the file `unit_testing.aber`:
```aber
std::use_prelude;

fn foo(n) { n.+ 1 };

fn (test) test() {
	assert_eq(foo(1), 1).?;
};

fn main() {
	print "result: {}" (run foo(1));
};
```
Сompiler command:
```
aberc --run unit_testing.aber
```
Output:
```
result: 2
```
Сompiler command:
```
aberc --test unit_testing.aber
```
Output:
```
The crate::test failed at ./unit_testing.aber:5:1:
    assert_eq(foo(1), 1).?;
left: 2
right: 1
```
# Specification
- [Syntax](./Syntax/_.md)
- [Semantics](./Semantics/_.md)