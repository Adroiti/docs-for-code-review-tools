Pattern: Missing use of object literal

Issue: -

## Description

Prefer object literals over image and color inits.

Examples of **correct** code:
```swift
let image = #imageLiteral(resourceName: "image.jpg")


let color = #colorLiteral(red: 0.9607843161, green: 0.7058823705, blue: 0.200000003, alpha: 1)


let image = UIImage(named: aVariable)


let image = UIImage(named: "interpolated \(variable)")


let color = UIColor(red: value, green: value, blue: value, alpha: 1)


let image = NSImage(named: aVariable)


let image = NSImage(named: "interpolated \(variable)")


let color = NSColor(red: value, green: value, blue: value, alpha: 1)

```
Examples of **incorrect** code:
```swift

let image = ↓UIImage(named: "foo")


let color = ↓UIColor(red: 0.3, green: 0.3, blue: 0.3, alpha: 1)


let color = ↓UIColor(red: 100 / 255.0, green: 50 / 255.0, blue: 0, alpha: 1)


let color = ↓UIColor(white: 0.5, alpha: 1)


let image = ↓NSImage(named: "foo")


let color = ↓NSColor(red: 0.3, green: 0.3, blue: 0.3, alpha: 1)


let color = ↓NSColor(red: 100 / 255.0, green: 50 / 255.0, blue: 0, alpha: 1)


let color = ↓NSColor(white: 0.5, alpha: 1)


let image = ↓UIImage.init(named: "foo")


let color = ↓UIColor.init(red: 0.3, green: 0.3, blue: 0.3, alpha: 1)


let color = ↓UIColor.init(red: 100 / 255.0, green: 50 / 255.0, blue: 0, alpha: 1)


let color = ↓UIColor.init(white: 0.5, alpha: 1)


let image = ↓NSImage.init(named: "foo")


let color = ↓NSColor.init(red: 0.3, green: 0.3, blue: 0.3, alpha: 1)


let color = ↓NSColor.init(red: 100 / 255.0, green: 50 / 255.0, blue: 0, alpha: 1)


let color = ↓NSColor.init(white: 0.5, alpha: 1)

```

## Further Reading

* [SwiftLint - Object Literal](https://github.com/realm/SwiftLint/blob/master/Rules.md#object-literal)