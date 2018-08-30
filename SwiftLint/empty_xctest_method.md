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


class Foobar {
    func setUp() {}

    func tearDown() {}

    func testFoo() {}
}


class TotoTests: XCTestCase {
    func setUp(with object: Foobar) {}

    func tearDown(object: Foobar) {}

    func testFoo(_ foo: Foobar) {}

    func testBar(bar: (String) -> Int) {}
}


class TotoTests: XCTestCase {
    func testFoo() { XCTAssertTrue(foobar?.foo) }

    func testBar() { XCTAssertFalse(foobar?.bar) }
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


class TotoTests: XCTestCase {
    override ↓func setUp() {}

    override ↓func tearDown() {}

    ↓func testFoo() {}

    func helperFunction() {}
}


class TotoTests: XCTestCase {
    override ↓func setUp() {
        // comment...
    }

    override ↓func tearDown() {
        // comment...
        // comment...
    }

    ↓func testFoo() {
        // comment...

        // comment...

        // comment...
    }

    ↓func testBar() {
        /*
         * comment...
         *
         * comment...
         *
         * comment...
         */
    }

    func helperFunction() {
    }
}


class FooTests: XCTestCase {
    override ↓func setUp() {}
}

class BarTests: XCTestCase {
    ↓func testFoo() {}
}

```

## Further Reading

* [SwiftLint - Empty XCTest Method](https://github.com/realm/SwiftLint/blob/master/Rules.md#empty-xctest-method)