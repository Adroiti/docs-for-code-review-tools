Pattern: Missing use of key in widget constructor

Issue: -

## Description

It's a good practice to expose the ability to provide a key when creating public widgets.

Example of **incorrect** code:

```dart
class MyPublicWidget extends StatelessWidget {
}
```

Example of **correct** code:

```dart
class MyPublicWidget extends StatelessWidget {
 MyPublicWidget({Key key}) : super(key: key);
}
```

## Further Reading

* [Linter for Dart - use_key_in_widget_constructors](https://dart.dev/tools/linter-rules/use_key_in_widget_constructors)