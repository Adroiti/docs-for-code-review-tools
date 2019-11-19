Pattern: Missing use of `??=`

Issue: -

## Description

As Dart has the `??=` operator, it is advisable to use it where applicable to improve the brevity of your code.

Example of **incorrect** code:
```dart
String get fullName {
 if (_fullName == null) {
  _fullName = getFullUserName(this);
 }
 return _fullName;
}
```

Example of **correct** code:
```dart
String get fullName {
 return _fullName ??= getFullUserName(this);;
}
```

## Further Reading

* [Linter for Dart - prefer_conditional_assignment](https://dart-lang.github.io/linter/lints/prefer_conditional_assignment.html)