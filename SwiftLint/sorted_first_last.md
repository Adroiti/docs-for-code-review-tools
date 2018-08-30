Pattern: Use of `sorted().first`/`sorted().last` instead of `min()`/`max()`

Issue: -

## Description

Prefer using `min()` or `max()` over `sorted().first` or `sorted().last`

Examples of **correct** code:
```swift
let min = myList.min()


let min = myList.min(by: { $0 < $1 })


let min = myList.min(by: >)


let min = myList.max()


let min = myList.max(by: { $0 < $1 })

```
Examples of **incorrect** code:
```swift

↓myList.sorted().first


↓myList.sorted(by: { $0.description < $1.description }).first


↓myList.sorted(by: >).first


↓myList.map { $0 + 1 }.sorted().first


↓myList.sorted(by: someFunction).first


↓myList.map { $0 + 1 }.sorted { $0.description < $1.description }.first


↓myList.sorted().last


↓myList.sorted().last?.something()


↓myList.sorted(by: { $0.description < $1.description }).last


↓myList.map { $0 + 1 }.sorted().last


↓myList.sorted(by: someFunction).last


↓myList.map { $0 + 1 }.sorted { $0.description < $1.description }.last


↓myList.map { $0 + 1 }.sorted { $0.first < $1.first }.last

```

## Further Reading

* [SwiftLint - Min or Max over Sorted First or Last](https://github.com/realm/SwiftLint/blob/master/Rules.md#min-or-max-over-sorted-first-or-last)