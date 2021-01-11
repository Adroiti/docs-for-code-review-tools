Pattern: Malformed test case accessibility

Issue: -

## Description

Test cases should only contain private non-test members.

Examples of **correct** code:

```swift
let foo: String?

class FooTests: XCTestCase {
    static let allTests: [String] = []

    private let foo: String {
        let nestedMember = "hi"
        return nestedMember
    }

    override static func setUp() {
        super.setUp()
    }

    override func setUp() {
        super.setUp()
    }

    override func setUpWithError() throws {
        try super.setUpWithError()
    }

    override static func tearDown() {
        super.tearDown()
    }

    override func tearDown() {
        super.tearDown()
    }

    override func tearDownWithError() {
        try super.tearDownWithError()
    }

    override func someFutureXCTestFunction() {
        super.someFutureXCTestFunction()
    }

    func testFoo() {
        XCTAssertTrue(true)
    }
}
```

Examples of **incorrect** code:

```swift
class FooTests: XCTestCase {
    ↓var foo: String?
    ↓let bar: String?

    ↓static func foo() {}

    ↓func setUp(withParam: String) {}

    ↓func foobar() {}

    ↓func not_testBar() {}

    ↓enum Nested {}

    ↓static func testFoo() {}

    ↓static func allTests() {}
}

final class BarTests: XCTestCase {
    ↓class Nested {}
}
```

## Further Reading

* [SwiftLint - Test case accessibility](https://realm.github.io/SwiftLint/test_case_accessibility.html)