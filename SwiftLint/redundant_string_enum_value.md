Pattern: Redundant string enum value

Issue: -

## Description

String enum values can be omitted when they are equal to the enumcase name.

Examples of **correct** code:
```swift
enum Numbers: String {
 case one
 case two
}


enum Numbers: Int {
 case one = 1
 case two = 2
}


enum Numbers: String {
 case one = "ONE"
 case two = "TWO"
}


enum Numbers: String {
 case one = "ONE"
 case two = "two"
}


enum Numbers: String {
 case one, two
}

```
Examples of **incorrect** code:
```swift

enum Numbers: String {
 case one = ↓"one"
 case two = ↓"two"
}


enum Numbers: String {
 case one = ↓"one", two = ↓"two"
}


enum Numbers: String {
 case one, two = ↓"two"
}

```

## Further Reading

* [SwiftLint - Redundant String Enum Value](https://realm.github.io/SwiftLint/redundant_string_enum_value.html)