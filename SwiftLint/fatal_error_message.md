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

* [SwiftLint - Fatal Error Message](https://realm.github.io/SwiftLint/fatal_error_message.html)