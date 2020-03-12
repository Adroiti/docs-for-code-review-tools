Pattern: Invalid `@IBInspectable`

Issue: -

## Description

`@IBInspectable` should be applied to variables only, have its type explicit and be of a supported type.

Examples of **correct** code:
```swift
class Foo {
  @IBInspectable private var x: Int
}


class Foo {
  @IBInspectable private var x: String?
}


class Foo {
  @IBInspectable private var x: String!
}


class Foo {
  @IBInspectable private var count: Int = 0
}


class Foo {
  private var notInspectable = 0
}


class Foo {
  private let notInspectable: Int
}


class Foo {
  private let notInspectable: UInt8
}

```
Examples of **incorrect** code:
```swift

class Foo {
  @IBInspectable private ↓let count: Int
}


class Foo {
  @IBInspectable private ↓var insets: UIEdgeInsets
}


class Foo {
  @IBInspectable private ↓var count = 0
}


class Foo {
  @IBInspectable private ↓var count: Int?
}


class Foo {
  @IBInspectable private ↓var count: Int!
}


class Foo {
  @IBInspectable private ↓var x: ImplicitlyUnwrappedOptional<Int>
}


class Foo {
  @IBInspectable private ↓var count: Optional<Int>
}


class Foo {
  @IBInspectable private ↓var x: Optional<String>
}


class Foo {
  @IBInspectable private ↓var x: ImplicitlyUnwrappedOptional<String>
}

```

## Further Reading

* [Apple Developer - Render and inspect your custom views](https://help.apple.com/xcode/mac/8.0/#/devf60c1c514)
* [SwiftLint - Valid IBInspectable](https://realm.github.io/SwiftLint/valid_ibinspectable.html)