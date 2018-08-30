Pattern: Missing ACL keyword

Issue: -

## Description

All declarations should specify Access Control Level keywords explicitly.

Examples of **correct** code:
```swift
internal enum A {}


public final class B {}


private struct C {}


internal enum A {
 internal enum B {}
}


internal final class Foo {}


internal
class Foo {  private let bar = 5 }


internal func a() { let a =  }


private func a() { func innerFunction() { } }


private enum Foo { enum Bar { } }


private struct C { let d = 5 }


internal protocol A {
    func b()
}


internal protocol A {
    var b: Int
}


internal class A { deinit {} }

```
Examples of **incorrect** code:
```swift

enum A {}


final class B {}


internal struct C { let d = 5 }


public struct C { let d = 5 }


func a() {}


internal let a = 0
func b() {}

```

## Further Reading

* [SwiftLint - Explicit ACL](https://github.com/realm/SwiftLint/blob/master/Rules.md#explicit-acl)