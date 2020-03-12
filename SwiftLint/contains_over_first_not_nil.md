Pattern: Use of `first(where:) != nil`

Issue: -

## Description

Prefer `contains` over `first(where:) != nil`.

Examples of **correct** code:
```swift
let first = myList.first(where: { $0 % 2 == 0 })


let first = myList.first { $0 % 2 == 0 }

```
Examples of **incorrect** code:
```swift

↓myList.first { $0 % 2 == 0 } != nil


↓myList.first(where: { $0 % 2 == 0 }) != nil


↓myList.map { $0 + 1 }.first(where: { $0 % 2 == 0 }) != nil


↓myList.first(where: someFunction) != nil


↓myList.map { $0 + 1 }.first { $0 % 2 == 0 } != nil

```

## Further Reading

* [SwiftLint - Contains over first not nil](https://realm.github.io/SwiftLint/contains_over_first_not_nil.html)