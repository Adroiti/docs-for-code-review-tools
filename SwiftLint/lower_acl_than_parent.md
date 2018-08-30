Pattern: Malformed _ACL_ for parent-definition 

Issue: -

## Description

Ensure definitions have a lower Access Control Level than their enclosing parent

Examples of **correct** code:
```swift
public struct Foo { public func bar() {} }


internal struct Foo { func bar() {} }


struct Foo { func bar() {} }


open class Foo { public func bar() {} }


open class Foo { open func bar() {} }


fileprivate struct Foo { private func bar() {} }


private struct Foo { private func bar(id: String) }


extension Foo { public func bar() {} }


private struct Foo { fileprivate func bar() {} }


private func foo(id: String) {}

```
Examples of **incorrect** code:
```swift

struct Foo { public func bar() {} }


enum Foo { public func bar() {} }


public class Foo { open func bar() }


class Foo { public private(set) var bar: String? }

```

## Further Reading

* [SwiftLint - Lower ACL than parent](https://github.com/realm/SwiftLint/blob/master/Rules.md#lower-acl-than-parent)