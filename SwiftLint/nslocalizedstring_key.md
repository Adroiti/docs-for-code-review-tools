Pattern: Missing static key for `NSLocalizedString`

Issue: -

## Description

Static strings should be used as key in `NSLocalizedString` in order to `genstrings` work.

Examples of **correct** code:

```swift
NSLocalizedString("key", comment: nil)

NSLocalizedString("key" + "2", comment: nil)
```

Examples of **incorrect** code:

```swift
NSLocalizedString(↓method(), comment: nil)

NSLocalizedString(↓"key_\(param)", comment: nil)
```

## Further Reading

* [SwiftLint - NSLocalizedString Key](https://github.com/realm/SwiftLint/blob/master/Rules.md#nslocalizedstring-key)