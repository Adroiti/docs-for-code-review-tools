Pattern: Use of wildcard variable

Issue: -

## Description

**DON'T** use wildcard parameters or variables.

Wildcard parameters and local variables
(e.g. underscore-only names like `_`, `__`, `___`, etc.) will
become non-binding in a future version of the Dart language.
Any existing code that uses wildcard parameters or variables will
break. In anticipation of this change, and to make adoption easier,
this lint disallows wildcard and variable parameter uses.


Example of **incorrect** code:

```dart
var _ = 1;
print(_); // LINT
```

```dart
void f(int __) {
 print(__); // LINT multiple underscores too
}
```

Example of **correct** code:

```dart
for (var _ in [1, 2, 3]) count++;
```

```dart
var [a, _, b, _] = [1, 2, 3, 4];
```

## Further Reading

* [Linter for Dart - no_wildcard_variable_uses](https://dart.dev/tools/linter-rules/no_wildcard_variable_uses)