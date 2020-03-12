Pattern: Missing description for `XCTFail()`

Issue: -

## Description

An `XCTFail` call should include a description of the assertion.

Examples of **correct** code:
```swift
func testFoo() {
    XCTFail("bar")
}


func testFoo() {
    XCTFail(bar)
}

```
Examples of **incorrect** code:
```swift

func testFoo() {
    ↓XCTFail()
}


func testFoo() {
    ↓XCTFail("")
}

```

## Further Reading

* [SwiftLint - XCTFail Message](https://realm.github.io/SwiftLint/xctfail_message.html)