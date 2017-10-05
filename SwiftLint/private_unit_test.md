Pattern: `private` unit test

Issue: -

## Description

Unit tests marked `private` are silently skipped.

Examples of **correct** code:
```swift
class FooTest: XCTestCase { func test1() {}
 internal func test2() {}
 public func test3() {}
 }


internal class FooTest: XCTestCase { func test1() {}
 internal func test2() {}
 public func test3() {}
 }


public class FooTest: XCTestCase { func test1() {}
 internal func test2() {}
 public func test3() {}
 }


private class Foo: NSObject { func test1() {}
 internal func test2() {}
 public func test3() {}
 }


private class Foo { func test1() {}
 internal func test2() {}
 public func test3() {}
 }


public class FooTest: XCTestCase { func test1(param: Int) {}
 }

```
Examples of **incorrect** code:
```swift

private ↓class FooTest: XCTestCase { func test1() {}
 internal func test2() {}
 public func test3() {}
 private func test4() {}
 }


class FooTest: XCTestCase { func test1() {}
 internal func test2() {}
 public func test3() {}
 private ↓func test4() {}
 }


internal class FooTest: XCTestCase { func test1() {}
 internal func test2() {}
 public func test3() {}
 private ↓func test4() {}
 }


public class FooTest: XCTestCase { func test1() {}
 internal func test2() {}
 public func test3() {}
 private ↓func test4() {}
 }

```

## Further Reading

* [SwiftLint - Private Unit Test](https://github.com/realm/SwiftLint/blob/master/Rules.md#private-unit-test)