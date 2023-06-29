Pattern: Missing use of `forEach`

Issue: -

## Description

Using `forEach` when you are only going to apply a function or method to all
elements of an iterable is a good practice because it makes your code more
terse.

Example of **incorrect** code:
```dart
for (final key in map.keys.toList()) {
 map.remove(key);
}
```

Example of **correct** code:
```dart
map.keys.toList().forEach(map.remove);
```

**NOTE:** Replacing a for each statement with a `forEach` call may change the 
behavior in the case where there are side-effects on the iterable itself.
```
for (final v in myList) {
 foo().f(v); // This code invokes foo() many times.
}

myList.forEach(foo().f); // But this one invokes foo() just once.
```

## Further Reading

* [Linter for Dart - prefer_foreach](https://dart.dev/tools/linter-rules/prefer_foreach)