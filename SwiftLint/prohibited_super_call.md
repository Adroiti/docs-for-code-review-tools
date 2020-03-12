Pattern: Prohibited call to `super`

Issue: -

## Description

Some methods should not call `super`.

Examples of **correct** code:
```swift
class VC: UIViewController {
	override func loadView() {
	}
}


class NSView {
	func updateLayer() {
		self.method1()	}
}

```
Examples of **incorrect** code:
```swift

class VC: UIViewController {
	override func loadView() {↓
		super.loadView()
	}
}


class VC: NSFileProviderExtension {
	override func providePlaceholder(at url: URL,completionHandler: @escaping (Error?) -> Void) {↓
		self.method1()
		super.providePlaceholder(at:url, completionHandler: completionHandler)
	}
}


class VC: NSView {
	override func updateLayer() {↓
		self.method1()
		super.updateLayer()
		self.method2()
	}
}


class VC: NSView {
	override func updateLayer() {↓
		defer {
			super.updateLayer()
		}
	}
}

```

## Further Reading

* [SwiftLint - Prohibited calls to super](https://realm.github.io/SwiftLint/prohibited_calls_to_super.html)