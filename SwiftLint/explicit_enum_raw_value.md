Pattern: Missing enum raw value

Issue: -

## Description

Enums should be explicitly assigned their raw values.

Examples of **correct** code:
```swift
enum Numbers {
 case int(Int)
 case short(Int16)
}


enum Numbers: Int {
 case one = 1
 case two = 2
}


enum Numbers: Double {
 case one = 1.1
 case two = 2.2
}


enum Numbers: String {
 case one = "one"
 case two = "two"
}


protocol Algebra {}
enum Numbers: Algebra {
 case one
}

```
Examples of **incorrect** code:
```swift

enum Numbers: Int {
 case one = 10, ↓two, three = 30
}


enum Numbers: NSInteger {
 case ↓one
}


enum Numbers: String {
 case ↓one
 case ↓two
}


enum Numbers: String {
 case ↓one, two = "two"
}


enum Numbers: Decimal {
 case ↓one, ↓two
}

```

## Further Reading

* [SwiftLint - Explicit Enum Raw Value](https://realm.github.io/SwiftLint/explicit_enum_raw_value.html)