Pattern: Use of `range(of:)` instead of `contains`

Issue: -

## Description

Prefer `contains` over `range(of:) != nil` and `range(of:) == nil`.

Examples of **correct** code:

```swift
let range = myString.range(of: "Test")


myString.contains("Test")


!myString.contains("Test")


resourceString.range(of: rule.regex, options: .regularExpression) != nil

```

Examples of **incorrect** code:

```swift

↓myString.range(of: "Test") != nil


↓myString.range(of: "Test") == nil

```
