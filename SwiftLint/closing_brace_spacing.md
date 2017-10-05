Pattern: Malformed `}`

Issue: -

## Description

Closing brace with closing parenthesis should not have any whitespaces in the middle.

Examples of **correct** code:
```swift
[].map({ })


[].map(
  { }
)

```
Examples of **incorrect** code:
```swift

[].map({ ↓} )


[].map({ ↓}	)

```

## Further Reading

* [SwiftLint - Closing Brace Spacing](https://github.com/realm/SwiftLint/blob/master/Rules.md#closing-brace-spacing)