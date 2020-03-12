Pattern: Use legacy random function

Issue: -

## Description

Prefer using `type.random(in:)` over legacy functions.

Examples of **correct** code:
```swift
Int.random(in: 0..<10)


Double.random(in: 8.6...111.34)


Float.random(in: 0 ..< 1)

```
Examples of **incorrect** code:
```swift

↓arc4random(10)


↓arc4random_uniform(83)


↓drand48(52)

```

## Further Reading

* [SwiftLint - Legacy Random](https://realm.github.io/SwiftLint/legacy_random.html)