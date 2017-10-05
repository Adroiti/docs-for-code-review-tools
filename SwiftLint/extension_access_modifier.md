Pattern: Missing extension access modifier

Issue: -

## Description

Prefer to use extension access modifiers.

Examples of **correct** code:
```swift
extension Foo: SomeProtocol {
   public var bar: Int { return 1 }
}


extension Foo {
   private var bar: Int { return 1 }
   public var baz: Int { return 1 }
}


extension Foo {
   private var bar: Int { return 1 }
   public func baz() {}
}


extension Foo {
   var bar: Int { return 1 }
   var baz: Int { return 1 }
}


public extension Foo {
   var bar: Int { return 1 }
   var baz: Int { return 1 }
}


extension Foo {
   private bar: Int { return 1 }
   private baz: Int { return 1 }
}


extension Foo {
   open bar: Int { return 1 }
   open baz: Int { return 1 }
}

```
Examples of **incorrect** code:
```swift

↓extension Foo {
   public var bar: Int { return 1 }
   public var baz: Int { return 1 }
}


↓extension Foo {
   public var bar: Int { return 1 }
   public func baz() {}
}


public extension Foo {
   public ↓func bar() {}
   public ↓func baz() {}
}

```

## Further Reading

* [SwiftLint - Extension Access Modifier](https://github.com/realm/SwiftLint/blob/master/Rules.md#extension-access-modifier)