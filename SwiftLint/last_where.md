Pattern: Use of `.filter { }.last` instead of `.last(where:)`

Issue: -

## Description

Prefer using `.last(where:)` over `.filter { }.last` in collections.

Examples of **correct** code:
```swift
kinds.filter(excludingKinds.contains).isEmpty && kinds.last == .identifier


myList.last(where: { $0 % 2 == 0 })


match(pattern: pattern).filter { $0.last == .identifier }


(myList.filter { $0 == 1 }.suffix(2)).last


collection.filter("stringCol = '3'").last

```
Examples of **incorrect** code:
```swift

↓myList.filter { $0 % 2 == 0 }.last


↓myList.filter({ $0 % 2 == 0 }).last


↓myList.map { $0 + 1 }.filter({ $0 % 2 == 0 }).last


↓myList.map { $0 + 1 }.filter({ $0 % 2 == 0 }).last?.something()


↓myList.filter(someFunction).last


↓myList.filter({ $0 % 2 == 0 })
.last


(↓myList.filter { $0 == 1 }).last

```

## Further Reading

* [SwiftLint - Last Where](https://github.com/realm/SwiftLint/blob/master/Rules.md#last-where)