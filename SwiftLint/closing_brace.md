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

* [SwiftLint - Closing Brace Spacing](https://realm.github.io/SwiftLint/closing_brace.html)