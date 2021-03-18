Pattern: Missing balanced `setUp`/`tearDown` methods

Issue: -

## Description

Test classes must implement balanced `setUp` and `tearDown` methods.

Examples of **correct** code:

```swift
final class FooTests: XCTestCase {
    override func setUp() {}
    override func tearDown() {}
}

final class FooTests: XCTestCase {
    override func setUpWithError() throws {}
    override func tearDown() {}
}

final class FooTests: XCTestCase {
    override func setUp() {}
    override func tearDownWithError() throws {}
}

final class FooTests: XCTestCase {
    override func setUpWithError() throws {}
    override func tearDownWithError() throws {}
}
final class BarTests: XCTestCase {
    override func setUpWithError() throws {}
    override func tearDownWithError() throws {}
}

struct FooTests {
    override func setUp() {}
}
class BarTests {
    override func setUpWithError() throws {}
}

final class FooTests: XCTestCase {
    override func setUpAlLExamples() {}
}

final class FooTests: XCTestCase {
    class func setUp() {}
    class func tearDown() {}
}

```

Examples of **incorrect** code:

```swift
final class ↓FooTests: XCTestCase {
    override func setUp() {}
}

final class ↓FooTests: XCTestCase {
    override func setUpWithError() throws {}
}

final class FooTests: XCTestCase {
    override func setUp() {}
    override func tearDownWithError() throws {}
}
final class ↓BarTests: XCTestCase {
    override func setUpWithError() throws {}
}

final class ↓FooTests: XCTestCase {
    class func tearDown() {}
}

final class ↓FooTests: XCTestCase {
    override func tearDown() {}
}

final class ↓FooTests: XCTestCase {
    override func tearDownWithError() throws {}
}

final class FooTests: XCTestCase {
    override func setUp() {}
    override func tearDownWithError() throws {}
}
final class ↓BarTests: XCTestCase {
    override func tearDownWithError() throws {}
}

```

## Further Reading

* [SwiftLint - Balanced XCTest life-cycle](https://realm.github.io/SwiftLint/balanced_xctest_lifecycle.html)