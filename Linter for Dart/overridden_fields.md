Pattern: Overriding field

Issue: -

## Description

Overriding fields is almost always done unintentionally. Regardless, it is a bad practice to do so.

Example of **incorrect** code:
```dart
class Base {
 Object field = 'lorem';

 Object something = 'change';
}

class Bad1 extends Base {
 @override
 final field = 'ipsum'; // LINT
}

class Bad2 extends Base {
 @override
 Object something = 'done'; // LINT
}
```

Example of **correct** code:
```dart
class Base {
 Object field = 'lorem';

 Object something = 'change';
}

class Ok extends Base {
 Object newField; // OK

 final Object newFinal = 'ignore'; // OK
}
```

Example of **correct** code:
```dart
abstract class BaseLoggingHandler {
 Base transformer;
}

class LogPrintHandler implements BaseLoggingHandler {
 @override
 Derived transformer; // OK
}
```

## Further Reading

* [Linter for Dart - overridden_fields](https://dart-lang.github.io/linter/lints/overridden_fields.html)