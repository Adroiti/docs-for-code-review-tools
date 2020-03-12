Pattern: Use of `filter(where:).isEmpty` instead of `contains`

Issue: -

## Description

Prefer `contains` over using `filter(where:).isEmpty`

Examples of **correct** code:

```swift
let result = myList.filter(where: { $0 % 2 == 0 }).count > 1


let result = myList.filter { $0 % 2 == 0 }.count > 1


let result = myList.filter(where: { $0 % 2 == 0 }).count == 1


let result = myList.filter { $0 % 2 == 0 }.count == 1


let result = myList.filter(where: { $0 % 2 == 0 }).count != 1


let result = myList.filter { $0 % 2 == 0 }.count != 1


let result = myList.contains(where: { $0 % 2 == 0 })


let result = !myList.contains(where: { $0 % 2 == 0 })


let result = myList.contains(10)

```
Examples of **incorrect** code:

```swift

let result = ↓myList.filter(where: { $0 % 2 == 0 }).isEmpty


let result = !↓myList.filter(where: { $0 % 2 == 0 }).isEmpty


let result = ↓myList.filter { $0 % 2 == 0 }.isEmpty


let result = ↓myList.filter(where: someFunction).isEmpty

```

## Further Reading

* [SwiftLint - Contains Over Filter Is Empty](https://realm.github.io/SwiftLint/contains_over_filter_is_empty.html)