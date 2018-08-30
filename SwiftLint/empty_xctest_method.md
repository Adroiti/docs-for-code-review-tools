Pattern: Empty _XCTest_ method

Issue: -

## Description

Empty _XCTest_ method should be avoided.

Examples of **correct** code:
```swift
class TotoTests: XCTestCase {
    var foobar: Foobar?

    override func setUp() {
        super.setUp()
        foobar = Foobar()
    }

    override func tearDown() {
        foobar = nil
        super.tearDown()
    }

    func testFoo() {
        XCTAssertTrue(foobar?.foo)
    }

    func testBar() {
        // comment...

        XCTAssertFalse(foobar?.bar)

        // comment...
    }
}

```
Examples of **incorrect** code:
```swift

class TotoTests: XCTestCase {
    override ↓func setUp() {
    }

    override ↓func tearDown() {

    }

    ↓func testFoo() {


    }

    ↓func testBar() {


    }

    func helperFunction() {
    }
}
```

## Further Reading

* [SwiftLint - Empty XCTest Method](https://github.com/realm/SwiftLint/blob/master/Rules.md#empty-xctest-method)