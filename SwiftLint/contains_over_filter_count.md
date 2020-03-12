Pattern: Use of `filter(where:).count` instead of `contains`

Issue: -

## Description

Prefer `contains` over comparing `filter(where:).count` to 0.

Examples of **correct** code:

```swift
let result = myList.filter(where: { $0 % 2 == 0 }).count > 1


let result = myList.filter { $0 % 2 == 0 }.count > 1


let result = myList.filter(where: { $0 % 2 == 0 }).count > 01


let result = myList.filter(where: { $0 % 2 == 0 }).count == 1


let result = myList.filter { $0 % 2 == 0 }.count == 1


let result = myList.filter(where: { $0 % 2 == 0 }).count == 01


let result = myList.filter(where: { $0 % 2 == 0 }).count != 1


let result = myList.filter { $0 % 2 == 0 }.count != 1


let result = myList.filter(where: { $0 % 2 == 0 }).count != 01


let result = myList.contains(where: { $0 % 2 == 0 })


let result = !myList.contains(where: { $0 % 2 == 0 })


let result = myList.contains(10)

```

Examples of **incorrect** code:
```swift

let result = ↓myList.filter(where: { $0 % 2 == 0 }).count > 0


let result = ↓myList.filter { $0 % 2 == 0 }.count > 0


let result = ↓myList.filter(where: someFunction).count > 0


let result = ↓myList.filter(where: { $0 % 2 == 0 }).count == 0


let result = ↓myList.filter { $0 % 2 == 0 }.count == 0


let result = ↓myList.filter(where: someFunction).count == 0


let result = ↓myList.filter(where: { $0 % 2 == 0 }).count != 0


let result = ↓myList.filter { $0 % 2 == 0 }.count != 0


let result = ↓myList.filter(where: someFunction).count != 0

```

## Further Reading

* [SwiftLint - Contains Over Filter Count](https://realm.github.io/SwiftLint/contains_over_filter_count.html)