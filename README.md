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
- [Syntax](./Syntax/_)
- [Semantics](./Semantics/_)