Pattern: Missing use of `.init(value:)`

Issue: -

## Description

Passing `NSNumber.init` or `NSDecimalNumber.init` as a function reference is dangerous as it can cause the wrong initializer to be used, causing crashes. Use `.init(value:)` instead.

Examples of **correct** code:

```swift
[0, 0.2].map(NSNumber.init(value:))

[0, 0.2].map { NSNumber(value: $0) }

[0, 0.2].map(NSDecimalNumber.init(value:))

[0, 0.2].map { NSDecimalNumber(value: $0) }
```

Examples of **incorrect** code:

```swift
[0, 0.2].map(↓NSNumber.init)

[0, 0.2].map(↓NSDecimalNumber.init)
```

## Further Reading

* [SwiftLint - NSNumber Init as Function Reference](https://realm.github.io/SwiftLint/ns_number_init_as_function_reference.html)