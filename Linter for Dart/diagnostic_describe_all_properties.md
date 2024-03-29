Pattern: Missing public property reference in `debug` method

Issue: -

## Description

Implementers of `Diagnosticable` should reference all public properties in
a `debugFillProperties(...)` or `debugDescribeChildren(...)` method
implementation to improve debuggability at runtime.

Public properties are defined as fields and getters that are

* not package-private (e.g., prefixed with `_`)
* not `static` or overriding
* not themselves `Widget`s or collections of `Widget`s

In addition, the "debug" prefix is treated specially for properties in Flutter.
For the purposes of diagnostics, a property `foo` and a prefixed property
`debugFoo` are treated as effectively describing the same property and it is
sufficient to refer to one or the other.

Example of **incorrect** code:
```dart
class Absorber extends Widget {
 bool get absorbing => _absorbing;
 bool _absorbing;
 bool get ignoringSemantics => _ignoringSemantics;
 bool _ignoringSemantics;
 @override
 void debugFillProperties(DiagnosticPropertiesBuilder properties) {
  super.debugFillProperties(properties);
  properties.add(DiagnosticsProperty<bool>('absorbing', absorbing));
  // Missing reference to ignoringSemantics
 }
} 
```

Example of **correct** code:
```dart
class Absorber extends Widget {
 bool get absorbing => _absorbing;
 bool _absorbing;
 bool get ignoringSemantics => _ignoringSemantics;
 bool _ignoringSemantics;
 @override
 void debugFillProperties(DiagnosticPropertiesBuilder properties) {
  super.debugFillProperties(properties);
  properties.add(DiagnosticsProperty<bool>('absorbing', absorbing));
  properties.add(DiagnosticsProperty<bool>('ignoringSemantics', ignoringSemantics));
 }
} 
```

## Further Reading

* [Linter for Dart - diagnostic_describe_all_properties](https://dart.dev/tools/linter-rules/diagnostic_describe_all_properties)