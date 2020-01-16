Pattern: Missing raw value for camel-cased codable enum

Issue: -

## Description

Camel cased cases of Codable String enums should have raw value.

Examples of **correct** code:

```swift
enum Numbers: Codable {
  case int(Int)
  case short(Int16)
}

enum Numbers: Int, Codable {
  case one = 1
  case two = 2
}

enum Numbers: Double, Codable {
  case one = 1.1
  case two = 2.2
}
```

Examples of **incorrect** code:

```swift
enum Status: String, Codable {
    case ok
    case ↓notAcceptable
    case maybeAcceptable = "maybe_acceptable"
}

enum Status: String, Decodable {
   case ok
   case ↓notAcceptable
   case maybeAcceptable = "maybe_acceptable"
}

enum Status: String, Encodable {
   case ok
   case ↓notAcceptable
   case maybeAcceptable = "maybe_acceptable"
}
```

## Further Reading

* [SwiftLint - Raw Value For Camel Cased Codable Enum](https://github.com/realm/SwiftLint/blob/master/Rules.md#raw_value_for_camel_cased_codable_enum)