Pattern: Unused `.enumerated()`

Issue: -

## Description

When the index or the item is not used, `.enumerated()` can be removed.

Examples of **correct** code:
```swift
for (idx, foo) in bar.enumerated() { }


for (_, foo) in bar.enumerated().something() { }


for (_, foo) in bar.something() { }


for foo in bar.enumerated() { }


for foo in bar { }


for (idx, _) in bar.enumerated().something() { }


for (idx, _) in bar.something() { }


for idx in bar.indices { }


for (section, (event, _)) in data.enumerated() {}

```
Examples of **incorrect** code:
```swift

for (↓_, foo) in bar.enumerated() { }


for (↓_, foo) in abc.bar.enumerated() { }


for (↓_, foo) in abc.something().enumerated() { }


for (idx, ↓_) in bar.enumerated() { }

```

## Further Reading

* [SwiftLint - Unused Enumerated](https://realm.github.io/SwiftLint/unused_enumerated.html)