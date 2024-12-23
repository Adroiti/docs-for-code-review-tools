Pattern: Missing use of `String(bytes:encoding:)`

Issue: -

## Description

Prefer failable `String(bytes:encoding:)` initializer when converting `Data` to `String`.

Example of **correct** code:

```swift
String(data: data, encoding: .utf8)
```

Example of **incorrect** code:

```swift
String(decoding: data, as: UTF8.self)
```

## Further Reading

* [SwiftLint - Optional Data -> String Conversion](https://realm.github.io/SwiftLint/optional_data_string_conversion.html)