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

* [SwiftLint - Unused Declaration](https://realm.github.io/SwiftLint/unused_declaration.html)