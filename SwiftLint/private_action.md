Pattern: Non-private `@IBAction`

Issue: -

## Description

IBActions should be private.

Examples of **correct** code:
```swift
class Foo {
	@IBAction private func barButtonTapped(_ sender: UIButton) {}
}


struct Foo {
	@IBAction private func barButtonTapped(_ sender: UIButton) {}
}


class Foo {
	@IBAction fileprivate func barButtonTapped(_ sender: UIButton) {}
}


struct Foo {
	@IBAction fileprivate func barButtonTapped(_ sender: UIButton) {}
}


private extension Foo {
	@IBAction func barButtonTapped(_ sender: UIButton) {}
}


fileprivate extension Foo {
	@IBAction func barButtonTapped(_ sender: UIButton) {}
}

```
Examples of **incorrect** code:
```swift

class Foo {
	@IBAction ↓func barButtonTapped(_ sender: UIButton) {}
}


struct Foo {
	@IBAction ↓func barButtonTapped(_ sender: UIButton) {}
}


class Foo {
	@IBAction public ↓func barButtonTapped(_ sender: UIButton) {}
}


struct Foo {
	@IBAction public ↓func barButtonTapped(_ sender: UIButton) {}
}


class Foo {
	@IBAction internal ↓func barButtonTapped(_ sender: UIButton) {}
}


struct Foo {
	@IBAction internal ↓func barButtonTapped(_ sender: UIButton) {}
}


extension Foo {
	@IBAction ↓func barButtonTapped(_ sender: UIButton) {}
}


extension Foo {
	@IBAction public ↓func barButtonTapped(_ sender: UIButton) {}
}


extension Foo {
	@IBAction internal ↓func barButtonTapped(_ sender: UIButton) {}
}


public extension Foo {
	@IBAction ↓func barButtonTapped(_ sender: UIButton) {}
}


internal extension Foo {
	@IBAction ↓func barButtonTapped(_ sender: UIButton) {}
}

```

## Further Reading

* [SwiftLint - Private Actions](https://realm.github.io/SwiftLint/private_actions.html)