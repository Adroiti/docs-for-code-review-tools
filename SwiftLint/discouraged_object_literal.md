Pattern: Use of object literal

Issue: -

## Description

Prefer initializers over object literals.

Examples of **correct** code:
```swift
let image = UIImage(named: aVariable)


let image = UIImage(named: "interpolated \(variable)")


let color = UIColor(red: value, green: value, blue: value, alpha: 1)


let image = NSImage(named: aVariable)


let image = NSImage(named: "interpolated \(variable)")


let color = NSColor(red: value, green: value, blue: value, alpha: 1)

```
Examples of **incorrect** code:
```swift

let image = ↓#imageLiteral(resourceName: "image.jpg")


let color = ↓#colorLiteral(red: 0.9607843161, green: 0.7058823705, blue: 0.200000003, alpha: 1)

```

## Further Reading

* [SwiftLint - Discouraged Object Literal](https://github.com/realm/SwiftLint/blob/master/Rules.md#discouraged-object-literal)