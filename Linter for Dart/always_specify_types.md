Pattern: Missing type annotation

Issue: -

## Description

Avoid `var` when specifying that a type is unknown and short-hands that elide
type annotations. Use `dynamic` if you are being explicit that the type is
unknown. Use `Object` if you are being explicit that you want an object that
implements `==` and `hashCode`.

Example of **correct** code:
```dart
int foo = 10;
final Bar bar = Bar();
String baz = 'hello';
const int quux = 20;
```

Example of **incorrect** code:
```dart
var foo = 10;
final bar = Bar();
const quux = 20;
```

NOTE: Using the the `@optionalTypeArgs` annotation in the `meta` package, API
authors can special-case type variables whose type needs to by dynamic but whose
declaration should be treated as optional. For example, suppose you have a
`Key` object whose type parameter you'd like to treat as optional. Using the
`@optionalTypeArgs` would look like this:

```
import 'package:meta/meta.dart';

@optionalTypeArgs
class Key<T> {
 ...
}

main() {
 Key s = Key(); // OK!
}
```

## Further Reading

* [Linter for Dart - always_specify_types](https://dart-lang.github.io/linter/lints/always_specify_types.html)
* [Flutter style guide](https://flutter.dev/style-guide/)