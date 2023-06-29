Pattern: Unnecessary `break`

Issue: -

## Description

Only use a `break` in a non-empty switch case statement if you need to break
before the end of the case body. Dart does not support fallthrough execution
for non-empty cases, so `break`s at the end of non-empty switch case statements
are unnecessary.

Example of **incorrect** code:
```dart
switch (1) {
 case 1:
  print("one");
  break;
 case 2:
  print("two");
  break;
}
```

Example of **correct** code:
```dart
switch (1) {
 case 1:
  print("one");
 case 2:
  print("two");
}
```

```dart
switch (1) {
 case 1:
 case 2:
  print("one or two");
}
```

```dart
switch (1) {
 case 1:
  break;
 case 2:
  print("just two");
}
```

## Further Reading

* [Linter for Dart - unnecessary_breaks](https://dart.dev/tools/linter-rules/unnecessary_breaks)