Pattern: Missing use of case clause

Issue: -

## Description

Switching on instances of enum-like classes should be exhaustive.

Enum-like classes are defined as concrete (non-abstract) classes that have:
 * only private non-factory constructors
 * two or more static const fields whose type is the enclosing class and
 * no subclasses of the class in the defining library

**DO** define case clauses for all constants in enum-like classes.

Example of **incorrect** code:

```dart
class EnumLike {
 final int i;
 const E._(this.i);

 static const e = E._(1);
 static const f = E._(2);
 static const g = E._(3);
}

void bad(EnumLike e) {
 // Missing case.
 switch(e) { // LINT
  case E.e :
   print('e');
   break;
  case E.f :
   print('e');
   break;
 }
}
```

Example of **correct** code:
```dart
class EnumLike {
 final int i;
 const E._(this.i);

 static const e = E._(1);
 static const f = E._(2);
 static const g = E._(3);
}

void ok(E e) {
 // All cases covered.
 switch(e) { // OK
  case E.e :
   print('e');
   break;
  case E.f :
   print('e');
   break;
  case E.g :
   print('e');
   break;
 }
}
```

## Further Reading

* [Linter for Dart - exhaustive_cases](https://dart-lang.github.io/linter/lints/exhaustive_cases.html)