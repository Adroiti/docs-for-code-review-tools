Pattern: Missing use of shorthand syntax for optional binding

Issue: -

## Description

Use shorthand syntax for optional binding.

Examples of **correct** code:

```swift
if let i {}
if let i = a {}
guard let i = f() else {}
if var i = i() {}
if let i = i as? Foo {}
guard let `self` = self else {}
while var i { i = nil }
```

Examples of **incorrect** code:

```swift
if ↓let i = i {}
if ↓let self = self {}
if ↓var `self` = `self` {}
if i > 0, ↓let j = j {}
if ↓let i = i, ↓var j = j {}

guard ↓let i = i else {}
guard ↓let self = self else {}
guard ↓var `self` = `self` else {}
guard i > 0, ↓let j = j else {}
guard ↓let i = i, ↓var j = j else {}

while ↓var i = i { i = nil }
```

## Further Reading

* [SwiftLint - Shorthand Optional Binding](https://realm.github.io/SwiftLint/shorthand_optional_binding.html)