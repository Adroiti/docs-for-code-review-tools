Pattern: Use of optional collection instead of empty collection

Issue: -

## Description

Prefer empty collection over optional collection.

Examples of **correct** code:
```swift
var foo: [Int]


var foo: [String: Int]


var foo: Set<String>


var foo: [String: [String: Int]]


let foo: [Int] = []
```
Examples of **incorrect** code:
```swift

↓var foo: [Int]?


↓var foo: [String: Int]?


↓var foo: Set<String>?


↓let foo: [Int]? = nil


↓let foo: [String: Int]? = nil

```

## Further Reading

* [SwiftLint - Discouraged Optional Collection](https://realm.github.io/SwiftLint/discouraged_optional_collection.html)