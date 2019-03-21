Pattern: `@IBOutlet` declared as `weak`

Issue: -

## Description

`@IBOutlet`s shouldn't be declared as `weak`.

Examples of **correct** code:
```swift
class ViewController: UIViewController {
    @IBOutlet var label: UILabel?
}


class ViewController: UIViewController {
    weak var label: UILabel?
}

```
Examples of **incorrect** code:
```swift

class ViewController: UIViewController {
    @IBOutlet weak ↓var label: UILabel?
}


class ViewController: UIViewController {
    @IBOutlet unowned ↓var label: UILabel!
}


class ViewController: UIViewController {
    @IBOutlet weak ↓var textField: UITextField?
}

```

## Further Reading

* [SwiftLint - Strong IBOutlet](https://github.com/realm/SwiftLint/blob/master/Rules.md#strong-iboutlet)