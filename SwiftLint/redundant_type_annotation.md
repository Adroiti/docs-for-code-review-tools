Pattern: Redundant type annotation

Issue: -

## Description

Variables should not have redundant type annotation

Examples of **correct** code:
```swift
var url = URL()


var url: CustomStringConvertible = URL()

```
Examples of **incorrect** code:
```swift

var url↓:URL=URL()


var url↓:URL = URL(string: "")


var url↓: URL = URL()


let url↓: URL = URL()


lazy var url↓: URL = URL()


let alphanumerics↓: CharacterSet = CharacterSet.alphanumerics


class ViewController: UIViewController {
    func someMethod() {
        let myVar↓: Int = Int(5)
    }
}

```

## Further Reading

* [SwiftLint - Redundant Type Annotation](https://github.com/realm/SwiftLint/blob/master/Rules.md#redundant-type-annotation)