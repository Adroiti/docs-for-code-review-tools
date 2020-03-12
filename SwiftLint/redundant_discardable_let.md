Pattern: Redundant discardable `let`

Issue: -

## Description

Prefer `_ = foo()` over `let _ = foo()` when discarding a result from a function.

Examples of **correct** code:
```swift
_ = foo()


if let _ = foo() { }


guard let _ = foo() else { return }


let _: ExplicitType = foo()


while let _ = SplashStyle(rawValue: maxValue) { maxValue += 1 }

```
Examples of **incorrect** code:
```swift

↓let _ = foo()


if _ = foo() { ↓let _ = bar() }

```

## Further Reading

* [SwiftLint - Redundant Discardable Let](https://realm.github.io/SwiftLint/redundant_discardable_let.html)