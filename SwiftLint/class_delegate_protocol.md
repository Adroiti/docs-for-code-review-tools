Pattern: Invalid class delegate protocol

Issue: -

## Description

Delegate protocols should be class-only so they can be weakly referenced.

Examples of **correct** code:
```swift
protocol FooDelegate: class {}


protocol FooDelegate: class, BarDelegate {}


protocol Foo {}


class FooDelegate {}


@objc protocol FooDelegate {}


@objc(MyFooDelegate)
 protocol FooDelegate {}


protocol FooDelegate: BarDelegate {}


protocol FooDelegate: AnyObject {}


protocol FooDelegate: NSObjectProtocol {}

```
Examples of **incorrect** code:
```swift

↓protocol FooDelegate {}


↓protocol FooDelegate: Bar {}

```

## Further Reading

* [SwiftLint - Class Delegate Protocol](https://realm.github.io/SwiftLint/class_delegate_protocol.html)