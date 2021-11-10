Pattern: Unnecessary constructor name

Issue: -

## Description

**PREFER** using the default unnamed Constructor over `.new`.

Given a class `C`, the named unnamed constructor `C.new` refers to the same constructor as the unnamed `C`. As such it adds nothing but visual noise to invocations and should be avoided (unless being used to identify a constructor tear-off).

Example of **incorrect** code:

```dart
class A {
  A.new(); // LINT
}

var a = A.new(); // LINT
```

Example of **correct** code:

```dart
class A {
  A.ok();
}

var a = A();
var aa = A.ok();
var makeA = A.new;
```

## Further Reading

* [Linter for Dart - unnecessary_constructor_name](https://dart-lang.github.io/linter/lints/unnecessary_constructor_name.html)