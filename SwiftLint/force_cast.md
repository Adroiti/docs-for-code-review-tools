Pattern: Use of `as!`

Issue: -

## Description

Force casts should be avoided.

Examples of **correct** code:
```swift
NSNumber() as? Int

```
Examples of **incorrect** code:
```swift

NSNumber() ↓as! Int

```

## Further Reading

* [SwiftLint - Force Cast](https://realm.github.io/SwiftLint/force_cast.html)