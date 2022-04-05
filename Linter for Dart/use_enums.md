Pattern: Missing use of enum

Issue: -

## Description

Classes that look like enumerations should be declared as `enum`s.

**DO** use enums where appropriate.

Candidates for enums are classes that:
 * are concrete,
 * are private or have only private generative constructors,
 * have two or more static const fields with the same type as the class,
 * have generative constructors that are only invoked at the top-level of the
  initialization expression of these static fields,
 * do not define `hashCode`, `==`, `values` or `index`,
 * do not extend any class other than Object, and
 * have no subclasses declared in the defining library.

Example of **incorrect** code:

```dart
class LogPriority {
 static const error = LogPriority._(1, 'Error');
 static const warning = LogPriority._(2, 'Warning');
 static const log = LogPriority._unknown('Log');

 final String prefix;
 final int priority;
 const LogPriority._(this.priority, this.prefix);
 const LogPriority._unknown(String prefix) : this._(-1, prefix);
}
```

Example of **correct** code:

```dart
enum LogPriority {
 error(1, 'Error'),
 warning(2, 'Warning'),
 log.unknown('Log');

 final String prefix;
 final int priority;
 const LogPriority(this.priority, this.prefix);
 const LogPriority.unknown(String prefix) : this(-1, prefix);
}
```

## Further Reading

* [Linter for Dart - use_enums](https://dart-lang.github.io/linter/lints/use_enums.html)