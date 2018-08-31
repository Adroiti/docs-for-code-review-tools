Pattern: Non-weak delegate

Issue: -

## Description

Delegates should be weak to avoid reference cycles.

Strong reference cycles happen when two class instances have strong references to each other. Their reference counts never go to zero so they never get deallocated.

Examples of **correct** code:
```swift
class Foo {
  weak var delegate: SomeProtocol?
}


class Foo {
  weak var someDelegate: SomeDelegateProtocol?
}


class Foo {
  weak var delegateScroll: ScrollDelegate?
}


class Foo {
  var scrollHandler: ScrollDelegate?
}


func foo() {
  var delegate: SomeDelegate
}


class Foo {
  var delegateNotified: Bool?
}


protocol P {
 var delegate: AnyObject? { get set }
}


class Foo {
 protocol P {
 var delegate: AnyObject? { get set }
}
}


class Foo {
 var computedDelegate: ComputedDelegate {
 return bar() 
} 
}

```
Examples of **incorrect** code:
```swift

class Foo {
  ↓var delegate: SomeProtocol?
}


class Foo {
  ↓var scrollDelegate: ScrollDelegate?
}

```

## Further Reading

* [SwiftLint - Weak Delegate](https://github.com/realm/SwiftLint/blob/master/Rules.md#weak-delegate)