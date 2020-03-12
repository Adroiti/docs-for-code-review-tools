Pattern: Comparing value to `.nan` constant

Issue: -

## Description

Instances of FloatingPoint (eg `Float`, `Double`, `CGFloat`, etc) should not be compared to a `NaN` using equal-to or not-equal-to operators. Doing so will result in unwanted or unpredicted behaviour, as comparisons using these operators will always return `false` and `true`, respectively.

Examples of **correct** code:

```swift
if myFloating.isNaN { ... }
if !myFloating.isNaN { ... }
```

Examples of **incorrect** code:

```swift
if myFloating == .nan { ... }  // Same as `if false`
if myFloating != .nan { ... }  // Same as `if true`
if myFloating >= .nan { ... }  // Same as `if false`
if myFloating < .nan { ... }   // Same as `if false`
```