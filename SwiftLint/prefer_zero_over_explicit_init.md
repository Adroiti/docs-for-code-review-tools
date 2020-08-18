Pattern: Use explicit init with zero parameters

Issue: -

## Description

Prefer `.zero` over explicit init with zero parameters (e.g. `CGPoint(x: 0, y: 0)`).

Examples of **correct** code:

```swift
CGRect(x: 0, y: 0, width: 0, height: 1)
CGPoint(x: 0, y: -1)
CGSize(width: 2, height: 4)
CGVector(dx: -5, dy: 0)
```

Examples of **incorrect** code:

```swift
↓CGPoint(x: 0, y: 0)
↓CGPoint(x: 0.000000, y: 0)
↓CGPoint(x: 0.000000, y: 0.000)
↓CGRect(x: 0, y: 0, width: 0, height: 0)
↓CGSize(width: 0, height: 0)
↓CGVector(dx: 0, dy: 0)
```

## Further Reading

* [SwiftLint - Prefer Zero Over Explicit Init](https://realm.github.io/SwiftLint/prefer_zero_over_explicit_init.html)