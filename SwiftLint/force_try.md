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

* [SwiftLint - Force Try](https://github.com/realm/SwiftLint/blob/master/Rules.md#force-try)