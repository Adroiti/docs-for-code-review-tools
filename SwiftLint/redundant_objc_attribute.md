Pattern: Redundant `@objc` attribute

Issue: -

## Description

Objective-C attribute `@objc` is redundant in declaration.

Examples of **correct** code:
```swift
@objc private var foo: String? {}


@IBInspectable private var foo: String? {}


@objc private func foo(_ sender: Any) {}


@IBAction private func foo(_ sender: Any) {}


@GKInspectable private var foo: String! {}


private @GKInspectable var foo: String! {}


@NSManaged var foo: String!


@objc @NSCopying var foo: String!


@objcMembers
class Foo {
  var bar: Any?
  @objc
  class Bar {
    @objc
    var foo: Any?
  }
}


@objc
extension Foo {
  var bar: Int {
    return 0
  }
}


extension Foo {
  @objc
  var bar: Int { return 0 }
}


@objc @IBDesignable
extension Foo {
  var bar: Int { return 0 }
}


@IBDesignable
extension Foo {
  @objc
  var bar: Int { return 0 }
  var fooBar: Int { return 1 }
}


@objcMembers
class Foo: NSObject {
  @objc
  private var bar: Int {
    return 0
  }
}


@objcMembers
class Foo {
    class Bar: NSObject {
        @objc var foo: Any
    }
}


@objcMembers
class Foo {
    @objc class Bar {}
}

```
Examples of **incorrect** code:
```swift

@objc @IBInspectable private ↓var foo: String? {}


@IBInspectable @objc private ↓var foo: String? {}


@objc @IBAction private ↓func foo(_ sender: Any) {}


@IBAction @objc private ↓func foo(_ sender: Any) {}


@objc @GKInspectable private ↓var foo: String! {}


@GKInspectable @objc private ↓var foo: String! {}


@objc @NSManaged private ↓var foo: String!


@NSManaged @objc private ↓var foo: String!


@objc @IBDesignable ↓class Foo {}


@objcMembers
class Foo {
  @objc ↓var bar: Any?
}


@objcMembers
class Foo {
  @objc ↓var bar: Any?
  @objc ↓var foo: Any?
  @objc
  class Bar {
    @objc
    var foo: Any?
  }
}


@objc
extension Foo {
  @objc
  ↓var bar: Int {
    return 0
  }
}


@objc @IBDesignable
extension Foo {
  @objc
  ↓var bar: Int {
    return 0
  }
}


@objcMembers
class Foo {
    @objcMembers
    class Bar: NSObject {
        @objc ↓var foo: Any
    }
}


@objc
extension Foo {
    @objc
    private ↓var bar: Int {
        return 0
    }
}

```
