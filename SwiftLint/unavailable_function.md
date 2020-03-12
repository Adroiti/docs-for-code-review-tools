Pattern: Unmarked unavailable function

Issue: -

## Description

Unimplemented functions should be marked as unavailable.

Examples of **correct** code:
```swift
class ViewController: UIViewController {
    @available(*, unavailable)
    public required init?(coder aDecoder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }
}


func jsonValue(_ jsonString: String) -> NSObject {
    let data = jsonString.data(using: .utf8)!
    let result = try! JSONSerialization.jsonObject(with: data, options: [])
    if let dict = (result as? [String: Any])?.bridge() {
        return dict
    } else if let array = (result as? [Any])?.bridge() {
        return array
    }
    fatalError()
}

```
Examples of **incorrect** code:
```swift

class ViewController: UIViewController {
    public required ↓init?(coder aDecoder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }
}


class ViewController: UIViewController {
    public required ↓init?(coder aDecoder: NSCoder) {
        let reason = "init(coder:) has not been implemented"
        fatalError(reason)
    }
}

```

## Further Reading

* [SwiftLint - Unavailable Function](https://realm.github.io/SwiftLint/unavailable_function.html)