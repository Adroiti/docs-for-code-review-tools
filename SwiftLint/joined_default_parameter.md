Pattern: Explicit use of default separator

Issue: -

## Description

Use to discourage explicit usage of the default separator.

Examples of **correct** code:
```swift
let foo = bar.joined()


let foo = bar.joined(separator: ",")


let foo = bar.joined(separator: toto)

```
Examples of **incorrect** code:
```swift

let foo = bar.joined(↓separator: "")


let foo = bar.filter(toto)
             .joined(↓separator: "")

```

## Further Reading

* [SwiftLint - Joined Default Parameter](https://github.com/realm/SwiftLint/blob/master/Rules.md#joined-default-parameter)