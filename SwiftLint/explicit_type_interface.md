Pattern: Missing explicit type interface

Issue: -

## Description

Properties should have a type interface.

Examples of **correct** code:
```swift
class Foo {
  var myVar: Int? = 0
}


class Foo {
  let myVar: Int? = 0
}


class Foo {
  static var myVar: Int? = 0
}


class Foo {
  class var myVar: Int? = 0
}

```
Examples of **incorrect** code:
```swift

class Foo {
  ↓var myVar = 0

}


class Foo {
  ↓let mylet = 0

}


class Foo {
  ↓static var myStaticVar = 0
}


class Foo {
  ↓class var myClassVar = 0
}

```

## Further Reading

* [SwiftLint - Explicit Type Interface](https://github.com/realm/SwiftLint/blob/master/Rules.md#explicit-type-interface)