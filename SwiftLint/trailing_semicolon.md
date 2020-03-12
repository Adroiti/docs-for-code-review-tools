Pattern: Trailing `;`

Issue: -

## Description

Lines should not have trailing semicolons.

Examples of **correct** code:
```swift
let a = 0

```
Examples of **incorrect** code:
```swift

let a = 0↓;


let a = 0↓;
let b = 1


let a = 0↓;;


let a = 0↓;    ;;


let a = 0↓; ; ;

```

## Further Reading

* [SwiftLint - Trailing Semicolon](https://realm.github.io/SwiftLint/trailing_semicolon.html)