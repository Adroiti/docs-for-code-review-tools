Pattern: Missing `super` call for overridden method

Issue: -

## Description

Some overridden methods should always call `super`.

Examples of **correct** code:
```swift
class VC: UIViewController {
	override func viewWillAppear(_ animated: Bool) {
		super.viewWillAppear(animated)
	}
}


class VC: UIViewController {
	override func viewWillAppear(_ animated: Bool) {
		self.method1()
		super.viewWillAppear(animated)
		self.method2()
	}
}


class VC: UIViewController {
	override func loadView() {
	}
}


class Some {
	func viewWillAppear(_ animated: Bool) {
	}
}


class VC: UIViewController {
	override func viewDidLoad() {
		defer {
			super.viewDidLoad()
		}
	}
}

```
Examples of **incorrect** code:
```swift

class VC: UIViewController {
	override func viewWillAppear(_ animated: Bool) {↓
		//Not calling to super
		self.method()
	}
}


class VC: UIViewController {
	override func viewWillAppear(_ animated: Bool) {↓
		super.viewWillAppear(animated)
		//Other code
		super.viewWillAppear(animated)
	}
}


class VC: UIViewController {
	override func didReceiveMemoryWarning() {↓
	}
}

```

## Further Reading

* [SwiftLint - Overridden methods call super](https://github.com/realm/SwiftLint/blob/master/Rules.md#overridden-methods-call-super)