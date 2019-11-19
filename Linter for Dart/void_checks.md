Pattern: Assigning to `void`

Issue: -

## Description

**DO NOT** assign to void.

Example of **incorrect** code:
```dart
class A<T> {
 T value;
 void test(T arg) { }
}

void main() {
 A<void> a = A<void>();
 a.value = 1; // LINT
 a.test(1); // LINT
}
```

## Further Reading

* [Linter for Dart - void_checks](https://dart-lang.github.io/linter/lints/void_checks.html)