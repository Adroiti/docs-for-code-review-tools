Pattern: Missing curly braces for flow control structure

Issue: -

## Description

**DO** use curly braces for all flow control structures.

Doing so avoids the [dangling else](http://en.wikipedia.org/wiki/Dangling_else) problem.

Example of **correct** code:
```dart
if (isWeekDay) {
 print('Bike to work!');
} else {
 print('Go dancing or read a book!');
}
```

There is one exception to this: an `if` statement with no `else` clause where
the entire `if` statement and the then body all fit in one line. In that case,
you may leave off the braces if you prefer:

Example of **correct** code:
```dart
if (arg == null) return defaultValue;
```

If the body wraps to the next line, though, use braces:

Example of **correct** code:
```dart
if (overflowChars != other.overflowChars) {
 return overflowChars < other.overflowChars;
}
```

Example of **incorrect** code:
```dart
if (overflowChars != other.overflowChars)
 return overflowChars < other.overflowChars;
```

## Further Reading

* [Linter for Dart - curly_braces_in_flow_control_structures](https://dart-lang.github.io/linter/lints/curly_braces_in_flow_control_structures.html)