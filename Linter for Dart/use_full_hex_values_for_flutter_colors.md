Pattern: Missing use of full hex value for Flutter color

Issue: -

## Description

Prefer an 8-digit hexadecimal integer(`0xFFFFFFFF`) to instantiate `Color`. Colors have four 8-bit channels, which adds up to 32 bits, so Colors are described using a 32 bit integer.

Example of **incorrect** code:
```dart
Color(1);
Color(0x000001);
```

Example of **correct** code:
```dart
Color(0x00000001);
```

## Further Reading

* [Linter for Dart - use_full_hex_values_for_flutter_colors](https://dart.dev/tools/linter-rules/use_full_hex_values_for_flutter_colors)