Pattern: Override in extension

Issue: -

## Description

Extensions shouldn't override declarations.

Examples of **correct** code:
```swift
extension Person {
  var age: Int { return 42 }
}


extension Person {
  func celebrateBirthday() {}
}


class Employee: Person {
  override func celebrateBirthday() {}
}


class Foo: NSObject {}
extension Foo {
    override var description: String { return "" }
}


struct Foo {
    class Bar: NSObject {}
}
extension Foo.Bar {
    override var description: String { return "" }
}

```
Examples of **incorrect** code:
```swift

extension Person {
  override ↓var age: Int { return 42 }
}


extension Person {
  override ↓func celebrateBirthday() {}
}

```

## Further Reading

* [SwiftLint - Override in Extension](https://github.com/realm/SwiftLint/blob/master/Rules.md#override-in-extension)