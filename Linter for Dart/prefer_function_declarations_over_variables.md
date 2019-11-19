Pattern: Missing use of function declaration to bind function to a name

Issue: -

## Description

As Dart allows local function declarations, it is a good practice to use them in the place of function literals.

Example of **incorrect** code:
```dart
void main() {
 var localFunction = () {
  ...
 };
}
```

Example of **correct** code:
```dart
void main() {
 localFunction() {
  ...
 }
}
```

## Further Reading

* [Linter for Dart - prefer_function_declarations_over_variables](https://dart-lang.github.io/linter/lints/prefer_function_declarations_over_variables.html)