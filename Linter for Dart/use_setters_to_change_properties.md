Pattern: Missing setter to change property

Issue: -

## Description

**DO** use a setter for operations that conceptually change a property.

Example of **incorrect** code:
```dart
rectangle.setWidth(3);
button.setVisible(false);
```

Example of **correct** code:
```dart
rectangle.width = 3;
button.visible = false;
```

## Further Reading

* [Linter for Dart - use_setters_to_change_properties](https://dart-lang.github.io/linter/lints/use_setters_to_change_properties.html)