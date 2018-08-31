Pattern: Use of `init(arrayLiteral:)`

Issue: -

## Description

Avoid calling this initializer directly. It is used by the compiler when you use an array literal. Instead, create a new set using an array literal as its value by enclosing a comma-separated list of values in square brackets. You can use an array literal anywhere a set is expected by the type context.

Examples of **correct** code:
```swift
let set: Set<Int> = [1, 2]


let set = Set(array)

```
Examples of **incorrect** code:
```swift

let set = ↓Set(arrayLiteral: 1, 2)


let set = ↓Set.init(arrayLiteral: 1, 2)

```

## Further Reading

* [Apple Developer - init(arrayLiteral:)](https://developer.apple.com/documentation/swift/set/1539368-init)
* [SwiftLint - Compiler Protocol Init](https://github.com/realm/SwiftLint/blob/master/Rules.md#compiler-protocol-init)