Pattern: Use of `assert(false)`

Issue: -

## Description

Prefer `assertionFailure()` and/or `preconditionFailure()` over `assert(false)`.

Examples of **correct** code:

```swift
assert(true)

assert(true, "foobar")

assert(true, "foobar", file: "toto", line: 42)

assert(false || true)

XCTAssert(false)
```

Examples of **incorrect** code:

```swift
↓assert(false)

↓assert(false, "foobar")

↓assert(false, "foobar", file: "toto", line: 42)

↓assert(   false    , "foobar")

```

## Further Reading

* [SwiftLint - Discouraged Assert](https://realm.github.io/SwiftLint/discouraged_assert.html)