Pattern: Missing use of collection literal

Issue: -

## Description

**DO** use collection literals when possible.

Example of **incorrect** code:
```dart
var points = new List();
var addresses = new Map();
var uniqueNames = new Set();
var ids = new LinkedHashSet();
var coordinates = new LinkedHashMap();
```

Example of **correct** code:
```dart
var points = [];
var addresses = <String,String>{};
var uniqueNames = <String>{};
var ids = <int>{};
var coordinates = <int,int>{};
```

**EXCEPTIONS:**

There are cases with `LinkedHashSet` or `LinkedHashMap` where a literal constructor
will trigger a type error so those will be excluded from the lint.

```
void main() {
 LinkedHashSet<int> linkedHashSet = LinkedHashSet.from([1, 2, 3]); // OK
 LinkedHashMap linkedHashMap = LinkedHashMap(); // OK
 
 printSet(LinkedHashSet<int>()); // LINT
 printHashSet(LinkedHashSet<int>()); // OK

 printMap(LinkedHashMap<int, int>()); // LINT
 printHashMap(LinkedHashMap<int, int>()); // OK
}

void printSet(Set<int> ids) => print('$ids!');
void printHashSet(LinkedHashSet<int> ids) => printSet(ids);
void printMap(Map map) => print('$map!');
void printHashMap(LinkedHashMap map) => printMap(map);
```

## Further Reading

* [Linter for Dart - prefer_collection_literals](https://dart-lang.github.io/linter/lints/prefer_collection_literals.html)