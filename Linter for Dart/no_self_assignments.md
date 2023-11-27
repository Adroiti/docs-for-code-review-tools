Pattern: Use of self-assignment

Issue: -

## Description

**DON'T** assign a variable to itself. Usually this is a mistake.

Example of **incorrect** code:

```dart
class C {
 int x;

 C(int x) {
  x = x;
 }
}
```

Example of **correct** code:
```dart
class C {
 int x;

 C(int x) : x = x;
}
```

Example of **correct** code:

```dart
class C {
 int x;

 C(int x) {
  this.x = x;
 }
}
```

Example of **incorrect** code:

```dart
class C {
 int _x = 5;

 int get x => _x;

 set x(int x) {
  _x = x;
  _customUpdateLogic();
 }

 void _customUpdateLogic() {
  print('updated');
 }

 void example() {
  x = x;
 }
}
```

Example of **correct** code:
```dart
class C {
 int _x = 5;

 int get x => _x;

 set x(int x) {
  _x = x;
  _customUpdateLogic();
 }

 void _customUpdateLogic() {
  print('updated');
 }

 void example() {
  _customUpdateLogic();
 }
}
```

Example of **incorrect** code:

```dart
class C {
 int x = 5;

 void update(C other) {
  this.x = this.x;
 }
}
```

Example of **correct** code:

```dart
class C {
 int x = 5;

 void update(C other) {
  this.x = other.x;
 }
}
```

## Further Reading

* [Linter for Dart - no_self_assignments](https://dart.dev/tools/linter-rules/no_self_assignments)