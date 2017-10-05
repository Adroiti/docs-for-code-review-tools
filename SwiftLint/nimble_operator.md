Pattern: Missing use of _Nimble_ operator

Issue: -

## Description

Prefer _Nimble_ operator overloads over free matcher functions.

Examples of **correct** code:
```swift
expect(seagull.squawk) != "Hi!"


expect("Hi!") == "Hi!"


expect(10) > 2


expect(10) >= 10


expect(10) < 11


expect(10) <= 10


expect(x) === x


expect(10) == 10


expect(object.asyncFunction()).toEventually(equal(1))


expect(actual).to(haveCount(expected))

```
Examples of **incorrect** code:
```swift

↓expect(seagull.squawk).toNot(equal("Hi"))


↓expect(12).toNot(equal(10))


↓expect(10).to(equal(10))


↓expect(10).to(beGreaterThan(8))


↓expect(10).to(beGreaterThanOrEqualTo(10))


↓expect(10).to(beLessThan(11))


↓expect(10).to(beLessThanOrEqualTo(10))


↓expect(x).to(beIdenticalTo(x))


expect(10) > 2
 ↓expect(10).to(beGreaterThan(2))

```

## Further Reading

* [SwiftLint - Nimble Operator](https://github.com/realm/SwiftLint/blob/master/Rules.md#nimble-operator)