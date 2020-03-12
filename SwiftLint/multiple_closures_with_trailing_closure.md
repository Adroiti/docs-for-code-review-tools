Pattern: Multiple closures with trailing closure

Issue: -

## Description

Trailing closure syntax should not be used when passing more than one closure argument.

Examples of **correct** code:
```swift
foo.map { $0 + 1 }


foo.reduce(0) { $0 + $1 }


if let foo = bar.map({ $0 + 1 }) {

}


foo.something(param1: { $0 }, param2: { $0 + 1 })


UIView.animate(withDuration: 1.0) {
    someView.alpha = 0.0
}

```
Examples of **incorrect** code:
```swift

foo.something(param1: { $0 }) ↓{ $0 + 1 }


UIView.animate(withDuration: 1.0, animations: {
    someView.alpha = 0.0
}) ↓{ _ in
    someView.removeFromSuperview()
}

```

## Further Reading

* [SwiftLint - Multiple Closures with Trailing Closure](https://realm.github.io/SwiftLint/multiple_closures_with_trailing_closure.html)