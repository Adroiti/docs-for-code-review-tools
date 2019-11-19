Pattern: Use of positional boolean parameter

Issue: -

## Description

Positional boolean parameters are a bad practice because they are ambiguous. 
Using named boolean parameters is much more readable because it
inherently describes what the boolean value represents.

Example of **incorrect** code:
```dart
Task(true);
Task(false);
ListBox(false, true, true);
Button(false);
```

Example of **correct** code:
```dart
Task.oneShot();
Task.repeating();
ListBox(scroll: true, showScrollbars: true);
Button(ButtonState.enabled);
```

## Further Reading

* [Linter for Dart - avoid_positional_boolean_parameters](https://dart-lang.github.io/linter/lints/avoid_positional_boolean_parameters.html)