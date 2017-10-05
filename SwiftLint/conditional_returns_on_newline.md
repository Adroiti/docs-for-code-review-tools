Pattern: Malformed newline for conditional return

Issue: -

## Description

Conditional statements should always return on the next line.

Examples of **correct** code:
```swift
guard true else {
 return true
}


guard true,
 let x = true else {
 return true
}


if true else {
 return true
}


if true,
 let x = true else {
 return true
}


if textField.returnKeyType == .Next {


if true { // return }


/*if true { */ return }

```
Examples of **incorrect** code:
```swift

↓guard true else { return }


↓if true { return }


↓if true { break } else { return }


↓if true { break } else {       return }


↓if true { return "YES" } else { return "NO" }

```

## Further Reading

* [SwiftLint - Conditional Returns on Newline](https://github.com/realm/SwiftLint/blob/master/Rules.md#conditional-returns-on-newline)