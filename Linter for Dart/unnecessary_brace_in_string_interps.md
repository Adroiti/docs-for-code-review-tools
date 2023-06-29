Pattern: Unnecessary braces in string interpolation

Issue: -

## Description

If you're just interpolating a simple identifier, and it's not immediately
followed by more alphanumeric text, the `{}` can and should be omitted.

Example of **correct** code:
```dart
print("Hi, $name!");
```

Example of **incorrect** code:
```dart
print("Hi, ${name}!");
```

## Further Reading

* [Linter for Dart - unnecessary_brace_in_string_interps](https://dart.dev/tools/linter-rules/unnecessary_brace_in_string_interps)