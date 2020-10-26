Pattern: Use of redundant argument value

Issue: -

## Description

Avoid redundant argument values.

**DON'T** declare arguments with values that match the defaults for the corresponding parameter.

Example of **incorrect** code:

```dart
void f({bool valWithDefault = true, bool val}) {
 ...
}

void main() {
 f(valWithDefault: true);
}
```

Example of **correct** code:
```dart
void f({bool valWithDefault = true, bool val}) {
 ...
}

void main() {
 f(valWithDefault: false);
 f();
}
```

## Further Reading

* [Linter for Dart - avoid_redundant_argument_values](https://dart-lang.github.io/linter/lints/avoid_redundant_argument_values.html)