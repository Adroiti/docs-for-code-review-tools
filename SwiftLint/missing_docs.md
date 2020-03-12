Pattern: Undocumented declaration

Issue: -

## Description

Declarations should be documented.

Examples of **correct** code:
```swift
/// docs
public class A {
/// docs
public func b() {}
}
/// docs
public class B: A { override public func b() {} }


import Foundation
/// docs
public class B: NSObject {
// no docs
override public var description: String { fatalError() } }

```
Examples of **incorrect** code:
```swift

public func a() {}


// regular comment
public func a() {}


/* regular comment */
public func a() {}


/// docs
public protocol A {
// no docs
var b: Int { get } }
/// docs
public struct C: A {

public let b: Int
}

```

## Further Reading

* [SwiftLint - Missing Docs](https://realm.github.io/SwiftLint/missing_docs.html)