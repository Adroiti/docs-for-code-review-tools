Pattern: Inert `defer`

Issue: -

## Description

If defer is at the end of its parent scope, it will be executed right where it is anyway.

Examples of **correct** code:
```swift
func example3() {
    defer { /* deferred code */ }

    print("other code")
}


func example4() {
    if condition {
        defer { /* deferred code */ }
        print("other code")
    }
}

```
Examples of **incorrect** code:
```swift

func example0() {
    ↓defer { /* deferred code */ }
}


func example1() {
    ↓defer { /* deferred code */ }
    // comment
}


func example2() {
    if condition {
        ↓defer { /* deferred code */ }
        // comment
    }
}

```

## Further Reading

* [SwiftLint - Inert Defer](https://github.com/realm/SwiftLint/blob/master/Rules.md#inert-defer)