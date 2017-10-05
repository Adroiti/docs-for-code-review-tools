Pattern: Call to initializer declared in compiler protocol

Issue: -

## Description

The initializers declared in compiler protocols such as `ExpressibleByArrayLiteral` shouldn't be called directly.

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

* [SwiftLint - Compiler Protocol Init](https://github.com/realm/SwiftLint/blob/master/Rules.md#compiler-protocol-init)