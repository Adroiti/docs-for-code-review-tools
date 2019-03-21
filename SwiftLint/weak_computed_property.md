Pattern: Use of `weak` in computed property

Issue: -

## Description

Adding `weak` to a computed property has no effect.

Examples of **correct** code:

```swift
class Foo {
    weak var delegate: SomeProtocol?
}


class Foo {
    var delegate: SomeProtocol?
}


class Foo {
    weak var delegate: SomeProtocol? {
        didSet {
            update(with: delegate)
        }
    }
}


class Foo {
    weak var delegate: SomeProtocol? {
        willSet {
            update(with: delegate)
        }
    }
}

```

Examples of **incorrect** code:

```swift

class Foo {
    weak var delegate: SomeProtocol? { return bar() }
}


class Foo {
    private weak var _delegate: SomeProtocol?

    ↓weak var delegate: SomeProtocol? {
        get { return _delegate }
        set { _delegate = newValue }
    }
}

```

## Further Reading

* [SwiftLint - Weak Computed Property](https://github.com/realm/SwiftLint/blob/master/Rules.md#weak-computed-property)