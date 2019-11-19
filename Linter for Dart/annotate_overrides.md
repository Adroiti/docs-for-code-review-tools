Pattern: Missing annotation for overridden method/field

Issue: -

## Description

**DO** annotate overridden methods and fields. This practice improves code readability and helps protect against unintentionally overriding superclass members.

Example of **correct** code:
```dart
abstract class Dog {
 String get breed;
 void bark() {}
}

class Husky extends Dog {
 @override
 final String breed = 'Husky';
 @override
 void bark() {}
}
```

Example of **incorrect** code:
```dart
class Cat {
 int get lives => 9;
}

class Lucky extends Cat {
 final int lives = 14;
}
```

## Further Reading

* [Linter for Dart - annotate_overrides](https://dart-lang.github.io/linter/lints/annotate_overrides.html)