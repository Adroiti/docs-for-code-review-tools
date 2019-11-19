Pattern: Missing use of generic function type alias

Issue: -

## Description

With the introduction of generic functions, function type aliases
(`typedef void F()`) couldn't express all of the possible kinds of
parameterization that users might want to express. Generic function type aliases
(`typedef F = void Function()`) fixed that issue.

For consistency and readability reasons, it's better to only use one syntax and thus prefer generic function type aliases.

Example of **incorrect** code:
```dart
typedef void F();
```

Example of **correct** code:
```dart
typedef F = void Function();
```

## Further Reading

* [Linter for Dart - prefer_generic_function_type_aliases](https://dart-lang.github.io/linter/lints/prefer_generic_function_type_aliases.html)