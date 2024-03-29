Pattern: Invalid case pattern

Issue: -

## Description

Some case expressions that are valid in Dart 2.19 and below will become an error
or have changed semantics when a library is upgraded to 3.0. This lint flags
those expressions in order to ease migration to Dart 3.0.

Some valid switch cases in 2.19 will become compile errors in Dart 3.0:

* Set literals
* Parenthesized expressions
* Calls to `identical()`.
* Unary operator expressions `!`, `-`, or `~` (except for `-` before an integer
 literal, which is a valid pattern and is fine)
* Binary operator expressions `!=`, `==`, `&`, `|`, `^`, `~/`, `>>`, `>>>`,
 `<<`, `+`, `-`, `*`, `/`, `%`, `<`, `<=`, `>`, `>=`, `??`.
* Conditional operator `?:`
* `.length` calls on strings
* `is` and `is!` expressions

Examples of all of them:

```dart
switch (obj) {
 case {1}: // Set literal.
 case (1): // Parenthesized expression.
 case identical(1, 2): // `identical()` call.
 case -pi: // Unary operator.
 case 1 + 2: // Binary operator.
 case true ? 1 : 2: // Conditional operator.
 case 'hi'.length: // .length call.
 case i is int: // is expression.
}
```

Some valid switch cases in 2.19 are also syntactically valid patterns, but the
pattern matching behavior may be different from the current constant equality
behavior. They are:

**List and map literals.** A list or map literal can appear as a constant in a
case:

```dart
switch (obj) {
 case [1, 2]: ...
 case {'k': 'v'}: ...
}
```

Currently, the case will only match if the incoming value has the same identity
as the constant. So:

```dart
test(List<int> list) {
 switch (list) {
  case [1, 2]: print('Matched'); break;
  default: print('Did not match'); break;
 }
}

main() {
 test(const [1, 2]); // Prints "Matched".
 test([1, 2]); // Prints "Did not match".
}
```

With patterns, a list or map literal becomes a list or map pattern. The pattern
destructures the incoming object and matches if the subpatterns all match. In
other words, list and map pattern match using something more like deep equality.

With Dart 3.0, the above program prints "Matched" twice.

**Constant constructor calls.** Similar to collections, you can construct a
constant instance of a class in a case:

```dart
class Point {
 final int x;
 final int y;
 const Point({this.x, this.y});
}

test(Point p) {
 switch (p) {
  case Point(x: 1, y: 2): print('Matched'); break;
  default: print('Did not match'); break;
 }
}

main() {
 test(const Point(1, 2)); // Prints "Matched".
 test(Point(1, 2)); // Prints "Did not match".
}
```

Again, like collections, the case currently only matches if the incoming value
has the same identity. With patterns, the `Point(...)` syntax becomes an object
pattern that destructures the incoming point, calls the `x` and `y` getters on
it and then matches the results of those against the corresponding subpatterns.

In this example, it will print "Matched" twice.

Note that object patterns only support named fields. So any constant constructor
in a case today that has positional arguments will become a compile-time error
when parsed as a pattern. A constant constructor call with no arguments is a
valid object pattern and only does a type test:

```dart
class Thing {
 const Thing();
}

test(Thing t) {
 switch (t) {
  case Thing(): print('Matched'); break;
  default: print('Did not match'); break;
 }
}

main() {
 test(const Thing()); // Prints "Matched".
 test(Thing()); // Prints "Did not match".
}
```

When interpreted as a pattern, this prints "Matched" twice.

**Wildcards.** Today, you can have a constant named `_`:

```dart
test(int n) {
 const _ = 3;
 switch (n) {
  case _: print('Matched'); break;
  default: print('Did not match'); break;
 }
}

main() {
 test(3); // Prints "Matched".
 test(5); // Prints "Did not match".
}
```

With patterns, the identifier `_` is treated as a pattern that matches all 
values, so this prints "Matched" twice.

**Logic operators.** The logic operators `&&` and `||` are valid constant
expressions and also valid patterns. As a constant expression, they simply
evaluate the expression to a boolean and match if the incoming value is equal to
that boolean value. So:

```dart
test(bool b) {
 switch (b) {
  case true && false: print('Matched'); break;
  default: print('Did not match'); break;
 }
}

main() {
 test(false); // Prints "Matched".
 test(true); // Prints "Did not match".
}
```

With Dart 3.0, these become patterns. The above example prints "Did not match"
twice because no boolean value can be both true and false.

Many of invalid cases can be mechanically changed to something that is valid
both in Dart today and valid and means the same in Dart 3.0.

**Parenthesized expressions:** Provided the inner expression is one that's not
broken in Dart 3.0, just discard the parentheses.

**List literals, map literals, set literals, and constant constructor calls:**
Put `const` before the literal or call. This turns it into a constant pattern
which preserves the current behavior:

Example of **incorrect** code:

```dart
case [1, 2]:
case {'k': 'v'}:
case {1, 2}:
case Point(1, 2):
```

Example of **correct** code:

```dart
case const [1, 2]:
case const {'k': 'v'}:
case const {1, 2}:
case const Point(1, 2):
```

* **Wildcards:** Rename the constant from `_` to something else. Since the name
is private, this can be done locally in the library without affecting other
code.

* **Everything else:** For any other invalid expression, you have to hoist the
expression out into a new named constant. For example, if you have code like
this:


Example of **incorrect** code:

```dart
switch (n) {
 case 1 + 2: ...
}
```

It can be fixed by changing it to:

Example of **correct** code:

 ```dart
const three = 1 + 2;

switch (n) {
 case three: ...
}
```

## Further Reading

* [Linter for Dart - invalid_case_patterns](https://dart.dev/tools/linter-rules/invalid_case_patterns)