Pattern: Use of leading underscore for local identifier

Issue: -

## Description

**DON’T** use a leading underscore for identifiers that aren't private. Dart
uses a leading underscore in an identifier to mark members and top-level
declarations as private. This trains users to associate a leading underscore
with one of those kinds of declarations. They see `_` and think "private".
There is no concept of "private" for local variables or parameters. When one of 
those has a name that starts with an underscore, it sends a confusing signal to
the reader. To avoid that, don't use leading underscores in those names.

**Exception**: An unused parameter can be named `_`, `__`, `___`, etc. This is
common practice in callbacks where you are passed a value but you don't need
to use it. Giving it a name that consists solely of underscores is the idiomatic
way to indicate that the value isn't used.

Example of **incorrect** code:

```dart
void print(String _name) {
 var _size = _name.length;
 ...
}
```
Example of **correct** code:

```dart
void print(String name) {
 var size = name.length;
 ...
}
```


```dart
[1,2,3].map((_) => print('Hello'));
```

## Further Reading

* [Linter for Dart - no_leading_underscores_for_local_identifiers](https://dart.dev/tools/linter-rules/no_leading_underscores_for_local_identifiers)