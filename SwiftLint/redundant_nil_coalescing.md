Pattern: Redundant `nil` coalescing

Issue: -

## Description

`nil` coalescing operator is only evaluated if the left-hand side is nil, coalescing operator with nil as right-hand side is redundant.

Examples of **correct** code:
```swift
var myVar: Int?; myVar ?? 0

```
Examples of **incorrect** code:
```swift

var myVar: Int? = nil; myVar↓ ?? nil


var myVar: Int? = nil; myVar↓??nil

```

## Further Reading

* [SwiftLint - Redundant Nil Coalescing](https://realm.github.io/SwiftLint/redundant_nil_coalescing.html)