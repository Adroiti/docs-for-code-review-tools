Pattern: Missing message for `fatalError()`

Issue: -

## Description

A `fatalError()` call should have a message.

Examples of **correct** code:
```swift
func foo() {
  fatalError("Foo")
}


func foo() {
  fatalError(x)
}

```
Examples of **incorrect** code:
```swift

func foo() {
  ↓fatalError("")
}


func foo() {
  ↓fatalError()
}

```

## Further Reading

* [SwiftLint - Fatal Error Message](https://github.com/realm/SwiftLint/blob/master/Rules.md#fatal-error-message)