Pattern: Malformed trailing closure

Issue: -

## Description

Trailing closure syntax should be used whenever possible.

Examples of **correct** code:
```swift
foo.map { $0 + 1 }


foo.bar()


foo.reduce(0) { $0 + 1 }


if let foo = bar.map({ $0 + 1 }) { }


foo.something(param1: { $0 }, param2: { $0 + 1 })


offsets.sorted { $0.offset < $1.offset }

```
Examples of **incorrect** code:
```swift

↓foo.map({ $0 + 1 })


↓foo.reduce(0, combine: { $0 + 1 })


↓offsets.sorted(by: { $0.offset < $1.offset })


↓foo.something(0, { $0 + 1 })

```

## Further Reading

* [SwiftLint - Trailing Closure](https://github.com/realm/SwiftLint/blob/master/Rules.md#trailing-closure)