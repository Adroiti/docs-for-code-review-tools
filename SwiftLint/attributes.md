Pattern: Malformed attribute

Issue: -

## Description

Attributes should be on their own lines in functions and types, but on the same line as variables and imports.

Examples of **correct** code:
```swift
@objc var x: String


@objc private var x: String


@nonobjc var x: String


@IBOutlet private var label: UILabel


@IBOutlet @objc private var label: UILabel
```
Examples of **incorrect** code:
```swift

@objc
 ↓var x: String


@objc

 ↓var x: String


@objc
 private ↓var x: String


@nonobjc
 ↓var x: String


@IBOutlet
 private ↓var label: UILabel

```

## Further Reading

* [SwiftLint - Attributes](https://realm.github.io/SwiftLint/attributes.html)