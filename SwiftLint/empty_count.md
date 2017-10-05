Pattern: Missing use of `isEmpty`

Issue: -

## Description

Prefer checking `isEmpty` over comparing `count` to zero.

Examples of **correct** code:
```swift
var count = 0


[Int]().isEmpty


[Int]().count > 1


[Int]().count == 1


discount == 0


order.discount == 0

```
Examples of **incorrect** code:
```swift

[Int]().↓count == 0


[Int]().↓count > 0


[Int]().↓count != 0


↓count == 0

```

## Further Reading

* [SwiftLint - Empty Count](https://github.com/realm/SwiftLint/blob/master/Rules.md#empty-count)