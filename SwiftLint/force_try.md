Pattern: Use of `try!`

Issue: -

## Description

Force tries should be avoided.

Examples of **correct** code:
```swift
func a() throws {}; do { try a() } catch {}

```
Examples of **incorrect** code:
```swift

func a() throws {}; ↓try! a()

```

## Further Reading

* [SwiftLint - Force Try](https://realm.github.io/SwiftLint/force_try.html)