Pattern: Fall-through in `switch` statement

Issue: -

## Description

Fall-throughs should be avoided.

Examples of **correct** code:
```swift
switch foo {
case .bar, .bar2, .bar3:
    something()
}

```
Examples of **incorrect** code:
```swift

switch foo {
case .bar:
    ↓fallthrough
case .bar2:
    something()
}

```

## Further Reading

* [SwiftLint - Fallthrough](https://github.com/realm/SwiftLint/blob/master/Rules.md#fallthrough)