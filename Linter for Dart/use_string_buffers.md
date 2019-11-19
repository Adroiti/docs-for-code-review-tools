Pattern: Missing use of string buffer

Issue: -

## Description

In most cases, using a string buffer is preferred for composing strings due to its improved performance.

Example of **incorrect** code:
```dart
String foo() {
 final buffer = '';
 for (int i = 0; i < 10; i++) {
  buffer += 'a'; // LINT
 }
 return buffer;
}
```

Example of **correct** code:
```dart
String foo() {
 final buffer = StringBuffer();
 for (int i = 0; i < 10; i++) {
  buffer.write('a');
 }
 return buffer.toString();
}
```

## Further Reading

* [Linter for Dart - use_string_buffers](https://dart-lang.github.io/linter/lints/use_string_buffers.html)