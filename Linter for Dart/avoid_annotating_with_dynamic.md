Pattern: Annotating with `dynamic`

Issue: -

## Description

As `dynamic` is the assumed return value of a function or method, it is usually
not necessary to annotate it.

Example of **incorrect** code:
```dart
dynamic lookUpOrDefault(String name, Map map, dynamic defaultValue) {
 var value = map[name];
 if (value != null) return value;
 return defaultValue;
}
```

Example of **correct** code:
```dart
lookUpOrDefault(String name, Map map, defaultValue) {
 var value = map[name];
 if (value != null) return value;
 return defaultValue;
}
```

## Further Reading

* [Linter for Dart - avoid_annotating_with_dynamic](https://dart.dev/tools/linter-rules/avoid_annotating_with_dynamic)