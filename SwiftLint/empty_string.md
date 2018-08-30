Pattern: Missing use of `.isEmpty` for string

Issue: -

## Description

Prefer checking `isEmpty` over comparing `string` to an empty string literal.

Examples of **correct** code:
```swift
myString.isEmpty


!myString.isEmpy

```
Examples of **incorrect** code:
```swift

myString↓ == ""


myString↓ != ""

```

## Further Reading

* [SwiftLint - Empty String](https://github.com/realm/SwiftLint/blob/master/Rules.md#empty-string)