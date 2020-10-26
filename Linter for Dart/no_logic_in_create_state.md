Pattern: Use of logic in `createState()`

Issue: -

## Description

Implementations of `createState()` should return a new instance
of a State object and do nothing more. Since state access is preferred 
via the `widget` field, passing data to `State` objects using custom
constructor parameters should also be avoided and so further, the State
constructor is required to be passed no arguments.

Example of **incorrect** code:

```dart
MyState global;

class MyStateful extends StatefulWidget {
 @override
 MyState createState() {
  global = MyState();
  return global;
 } 
}
```

```
class MyStateful extends StatefulWidget {
 @override
 MyState createState() => MyState()..field = 42;
}
```

```
class MyStateful extends StatefulWidget {
 @override
 MyState createState() => MyState(42);
}
```

Example of **correct** code:

```dart
class MyStateful extends StatefulWidget {
 @override
 MyState createState() {
  return MyState();
 }
}
```

## Further Reading

* [Linter for Dart - no_logic_in_create_state](https://dart-lang.github.io/linter/lints/no_logic_in_create_state.html)