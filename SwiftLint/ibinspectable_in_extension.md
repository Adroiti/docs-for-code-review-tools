Pattern: Use of `@IBInspectable` in extension

Issue: -

## Description

Extensions shouldn't add `@IBInspectable` properties.

Examples of **correct** code:

```swift
class Foo {
  @IBInspectable private var x: Int
}
```

Examples of **incorrect** code:

```swift
extension Foo {
  @IBInspectable private var x: Int
}
```

## Further Reading

* [SwiftLint - IBInspectable in Extension](https://realm.github.io/SwiftLint/ibinspectable_in_extension.html)