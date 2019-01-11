Pattern: Unused private declaration

Issue: -

## Description

Private declarations should be referenced in that file.

Examples of **correct** code:
```swift
private let kConstant = 0
_ = kConstant

```
Examples of **incorrect** code:
```swift

private let ↓kConstant = 0

```

## Further Reading

* [SwiftLint - Unused Private Declaration](https://github.com/realm/SwiftLint/blob/master/Rules.md#unused-private-declaration)