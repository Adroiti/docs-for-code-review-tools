Pattern: Wrong `super` order in constructor initialization list

Issue: -

## Description

**DO** place the `super` call last in a constructor initialization list.

Field initializers are evaluated in the order that they appear in the
constructor initialization list. If you place a `super()` call in the middle of
an initializer list, the superclass's initializers will be evaluated right then
before evaluating the rest of the subclass's initializers.

What it doesn't mean is that the superclass's constructor body will be executed
then. That always happens after all initializers are run regardless of where
`super` appears. It's vanishingly rare that the order of initializers matters,
so the placement of `super` in the list almost never matters either.

Getting in the habit of placing it last improves consistency, visually
reinforces when the superclass's constructor body is run, and may help
performance.

Example of **correct** code:
```dart
View(Style style, List children)
  : _children = children,
   super(style) {
```

Example of **incorrect** code:
```dart
View(Style style, List children)
  : super(style),
   _children = children {
```

**DEPRECATED:** In Dart 2, it is a compile-time error if a superinitializer
appears in an initializer list at any other position than at the end so this
rule is made redundant by the Dart analyzer's basic checks and is no longer
necessary.
 
The rule will be removed in a future Linter release.

## Further Reading

* [Linter for Dart - super_goes_last](https://dart-lang.github.io/linter/lints/super_goes_last.html)