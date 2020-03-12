Pattern: Missing `bundle` for `NSLocalizedString`

Issue: -

## Description

Calls to `NSLocalizedString` should specify the bundle which contains the strings file.

Examples of **correct** code:

```swift
NSLocalizedString("someKey", bundle: .main, comment: "test")


NSLocalizedString("someKey", tableName: "a",
                  bundle: Bundle(for: A.self),
                  comment: "test")


NSLocalizedString("someKey", tableName: "xyz",
                  bundle: someBundle, value: "test"
                  comment: "test")


arbitraryFunctionCall("something")

```

Examples of **incorrect** code:

```swift

↓NSLocalizedString("someKey", comment: "test")


↓NSLocalizedString("someKey", tableName: "a", comment: "test")


↓NSLocalizedString("someKey", tableName: "xyz",
                  value: "test", comment: "test")

```

## Further Reading

* [SwiftLint - NSLocalizedString Require Bundle](https://realm.github.io/SwiftLint/nslocalizedstring_require_bundle.html)