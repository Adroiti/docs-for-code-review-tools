Pattern: Unnecessary `late` modifier

Issue: -

## Description

**DO** not specify the `late` modifier for top-level and static variables
when the declaration contains an initializer. 

Top-level and static variables with initializers are already evaluated lazily
as if they are marked `late`.

Example of **incorrect** code:

```dart
late String badTopLevel = '';
```

Example of **correct** code:

```dart
String goodTopLevel = '';
```

Example of **incorrect** code:

```dart
class BadExample {
 static late String badStatic = '';
}
```

Example of **correct** code:

```dart
class GoodExample {
 late String goodStatic;
}
```

## Further Reading

* [Linter for Dart - unnecessary_late](https://dart.dev/tools/linter-rules/unnecessary_late)