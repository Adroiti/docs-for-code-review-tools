Pattern: Malformed `:`

Issue: -

## Description

Colons should be next to the identifier when specifying a type and next to the key in dictionary literals.

Examples of **correct** code:
```swift
let abc: Void


let abc: [Void: Void]


let abc: (Void, Void)


let abc: ([Void], String, Int)


let abc: [([Void], String, Int)]
```
Examples of **incorrect** code:
```swift

let ↓abc:Void


let ↓abc:  Void


let ↓abc :Void


let ↓abc : Void


let ↓abc : [Void: Void]
```

## Further Reading

* [SwiftLint - Colon](https://realm.github.io/SwiftLint/colon.html)