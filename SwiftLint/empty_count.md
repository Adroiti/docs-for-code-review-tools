Pattern: Missing use of `isEmpty`

Issue: -

## Description

Prefer checking `isEmpty` over comparing `count` to zero. For collections that don’t conform to `RandomAccessCollection`, accessing the count property iterates through the elements of the collection.

Examples of **correct** code:
```swift
var count = 0


[Int]().isEmpty


[Int]().count > 1


[Int]().count == 1

```
Examples of **incorrect** code:
```swift

[Int]().↓count == 0


[Int]().↓count > 0


[Int]().↓count != 0


↓count == 0

```

## Further Reading

* [Apple Developer - isEmpty](https://developer.apple.com/documentation/swift/array/1688398-isempty)
* [SwiftLint - Empty Count](https://realm.github.io/SwiftLint/empty_count.html)