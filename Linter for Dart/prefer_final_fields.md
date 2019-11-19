Pattern: Missing use of `final` field

Issue: -

## Description

Declaring fields as final when possible is a good practice because it helps
avoid accidental reassignments and allows the compiler to do optimizations.

Example of **incorrect** code:
```dart
class BadImmutable {
 var _label = 'hola mundo! BadImmutable'; // LINT
 var label = 'hola mundo! BadImmutable'; // OK
}
```

Example of **incorrect** code:
```dart
class MultipleMutable {
 var _label = 'hola mundo! GoodMutable', _offender = 'mumble mumble!'; // LINT
 var _someOther; // LINT

 MultipleMutable() : _someOther = 5;

 MultipleMutable(this._someOther);

 void changeLabel() {
  _label= 'hello world! GoodMutable';
 }
}
```

Example of **correct** code:
```dart
class GoodImmutable {
 final label = 'hola mundo! BadImmutable', bla = 5; // OK
 final _label = 'hola mundo! BadImmutable', _bla = 5; // OK
}
```

Example of **correct** code:
```dart
class GoodMutable {
 var _label = 'hola mundo! GoodMutable';

 void changeLabel() {
  _label = 'hello world! GoodMutable';
 }
}
```

Example of **incorrect** code:
```dart
class AssignedInAllConstructors {
 var _label; // LINT
 AssignedInAllConstructors(this._label);
 AssignedInAllConstructors.withDefault() : _label = 'Hello';
}
```

Example of **correct** code:
```dart
class NotAssignedInAllConstructors {
 var _label; // OK
 NotAssignedInAllConstructors();
 NotAssignedInAllConstructors.withDefault() : _label = 'Hello';
}
```

## Further Reading

* [Linter for Dart - prefer_final_fields](https://dart-lang.github.io/linter/lints/prefer_final_fields.html)