Pattern: Use of legacy constant

Issue: -

## Description

Struct-scoped constants are preferred over legacy global constants.

Examples of **correct** code:
```swift
CGRect.infinite


CGPoint.zero


CGRect.zero


CGSize.zero


NSPoint.zero


NSRect.zero


NSSize.zero


CGRect.null


CGFloat.pi


Float.pi

```
Examples of **incorrect** code:
```swift

↓CGRectInfinite


↓CGPointZero


↓CGRectZero


↓CGSizeZero


↓NSZeroPoint


↓NSZeroRect


↓NSZeroSize


↓CGRectNull


↓CGFloat(M_PI)


↓Float(M_PI)

```

## Further Reading

* [SwiftLint - Legacy Constant](https://github.com/realm/SwiftLint/blob/master/Rules.md#legacy-constant)