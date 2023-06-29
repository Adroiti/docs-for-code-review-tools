Pattern: Missing use of trailing comma

Issue: -

## Description

**DO** use trailing commas for all function calls and declarations unless the
function call or definition, from the start of the function name up to the
closing parenthesis, fits in a single line.

Example of **correct** code:

```dart
void run() {
 method(
  'does not fit on one line',
  'test test test test test test test test test test test',
 );
}
```

Example of **incorrect** code:

```dart
void run() {
 method('does not fit on one line',
   'test test test test test test test test test test test');
}
```

**Exception:** If the final parameter/argument is positional (vs named) and is
either a function literal implemented using curly braces, a literal map, a
literal set or a literal array. This exception only applies if the final
parameter does not fit entirely on one line.

**Note:** This lint rule assumes `dartfmt` has been run over the code and may
produce false positives until that has happened.

## Further Reading

* [Linter for Dart - require_trailing_commas](https://dart.dev/tools/linter-rules/require_trailing_commas)