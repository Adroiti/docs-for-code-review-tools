Pattern: Use of Interface Builder

Issue: -

## Description

Creating views using Interface Builder should be avoided.

Examples of **correct** code:
```swift
class ViewController: UIViewController {
    var label: UILabel!
}


class ViewController: UIViewController {
    @objc func buttonTapped(_ sender: UIButton) {}
}

```
Examples of **incorrect** code:
```swift

class ViewController: UIViewController {
    @IBOutlet ↓var label: UILabel!
}


class ViewController: UIViewController {
    @IBAction ↓func buttonTapped(_ sender: UIButton) {}
}

```

## Further Reading

* [SwiftLint - Prohibited Interface Builder](https://realm.github.io/SwiftLint/prohibited_interface_builder.html)