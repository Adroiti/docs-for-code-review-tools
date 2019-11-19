Pattern: Use of class with only static members

Issue: -

## Description

Creating classes with the sole purpose of providing utility or otherwise static
methods is discouraged. Dart allows functions to exist outside of classes for
this very reason.

Example of **incorrect** code:
```dart
class DateUtils {
 static DateTime mostRecent(List<DateTime> dates) {
  return dates.reduce((a, b) => a.isAfter(b) ? a : b);
 }
}

class _Favorites {
 static const mammal = 'weasel';
}
```

Example of **correct** code:
```dart
DateTime mostRecent(List<DateTime> dates) {
 return dates.reduce((a, b) => a.isAfter(b) ? a : b);
}

const _favoriteMammal = 'weasel';
```

## Further Reading

* [Linter for Dart - avoid_classes_with_only_static_members](https://dart-lang.github.io/linter/lints/avoid_classes_with_only_static_members.html)