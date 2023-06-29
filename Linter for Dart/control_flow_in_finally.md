Pattern: Use of control flow in `finally`

Issue: -

## Description

Using control flow in finally blocks will inevitably cause unexpected behavior that is hard to debug.

Example of **correct** code:
```dart
class Ok {
 double compliantMethod() {
  var i = 5;
  try {
   i = 1 / 0;
  } catch (e) {
   print(e); // OK
  }
  return i;
 }
}
```

Example of **incorrect** code:
```dart
class BadReturn {
 double nonCompliantMethod() {
  try {
   return 1 / 0;
  } catch (e) {
   print(e);
  } finally {
   return 1.0; // LINT
  }
 }
}
```

Example of **incorrect** code:
```dart
class BadContinue {
 double nonCompliantMethod() {
  for (var o in [1, 2]) {
   try {
    print(o / 0);
   } catch (e) {
    print(e);
   } finally {
    continue; // LINT
   }
  }
  return 1.0;
 }
}
```

Example of **incorrect** code:
```dart
class BadBreak {
 double nonCompliantMethod() {
  for (var o in [1, 2]) {
   try {
    print(o / 0);
   } catch (e) {
    print(e);
   } finally {
    break; // LINT
   }
  }
  return 1.0;
 }
}
```

## Further Reading

* [Linter for Dart - control_flow_in_finally](https://dart.dev/tools/linter-rules/control_flow_in_finally)