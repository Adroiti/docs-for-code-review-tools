Pattern: Non-private `@IBOutlet`

Issue: -

## Description

`@IBOutlet` should be private to avoid leaking `UIKit` to higher layers.

Examples of **correct** code:
```swift
class Foo {
  @IBOutlet private var label: UILabel?
}


class Foo {
  @IBOutlet private var label: UILabel!
}


class Foo {
  var notAnOutlet: UILabel
}


class Foo {
  @IBOutlet weak private var label: UILabel?
}


class Foo {
  @IBOutlet private weak var label: UILabel?
}

```
Examples of **incorrect** code:
```swift

class Foo {
  @IBOutlet ↓var label: UILabel?
}


class Foo {
  @IBOutlet ↓var label: UILabel!
}

```

## Further Reading

* [SwiftLint - Private Outlets](https://github.com/realm/SwiftLint/blob/master/Rules.md#private-outlets)