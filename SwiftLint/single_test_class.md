Pattern: Missing `QuickSpec`/`XCTestCase` for test file

Issue: -

## Description

Test files should contain a single `QuickSpec` or `XCTestCase` class.

Examples of **correct** code:
```swift
class FooTests {  }


class FooTests: QuickSpec {  }


class FooTests: XCTestCase {  }

```
Examples of **incorrect** code:
```swift

↓class FooTests: QuickSpec {  }
↓class BarTests: QuickSpec {  }


↓class FooTests: QuickSpec {  }
↓class BarTests: QuickSpec {  }
↓class TotoTests: QuickSpec {  }


↓class FooTests: XCTestCase {  }
↓class BarTests: XCTestCase {  }


↓class FooTests: XCTestCase {  }
↓class BarTests: XCTestCase {  }
↓class TotoTests: XCTestCase {  }


↓class FooTests: QuickSpec {  }
↓class BarTests: XCTestCase {  }


↓class FooTests: QuickSpec {  }
↓class BarTests: XCTestCase {  }
class TotoTests {  }

```

## Further Reading

* [SwiftLint - Single Test Class](https://realm.github.io/SwiftLint/single_test_class.html)