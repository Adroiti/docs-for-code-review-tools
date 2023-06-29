Pattern: Use of library private type in public API

Issue: -

## Description

**AVOID** using library private types in public APIs.

For the purposes of this lint, a public API is considered to be any top-level or
member declaration unless the declaration is library private or contained in a
declaration that's library private. The following uses of types are checked:

- the return type of a function or method,
- the type of any parameter of a function or method,
- the bound of a type parameter to any function, method, class, mixin,
 extension's extended type, or type alias,
- the type of any top level variable or field,
- any type used in the declaration of a type alias (for example
 `typedef F = _Private Function();`), or
- any type used in the `on` clause of an extension or a mixin

Example of **correct** code:

```dart
f(String s) { ... }
```

Example of **incorrect** code:

```dart
f(_Private p) { ... }
class _Private {}
```

## Further Reading

* [Linter for Dart - library_private_types_in_public_api](https://dart.dev/tools/linter-rules/library_private_types_in_public_api)