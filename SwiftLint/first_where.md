Pattern: Missing use of `.first(where:)`

Issue: -

## Description

Prefer using `.first(where:)` over `.filter { }.first` in collections.

Examples of **correct** code:
```swift
kinds.filter(excludingKinds.contains).isEmpty && kinds.first == .identifier


myList.first(where: { $0 % 2 == 0 })


match(pattern: pattern).filter { $0.first == .identifier }

```
Examples of **incorrect** code:
```swift

↓myList.filter { $0 % 2 == 0 }.first


↓myList.filter({ $0 % 2 == 0 }).first


↓myList.map { $0 + 1 }.filter({ $0 % 2 == 0 }).first


↓myList.map { $0 + 1 }.filter({ $0 % 2 == 0 }).first?.something()


↓myList.filter(someFunction).first


↓myList.filter({ $0 % 2 == 0 })
.first

```

## Further Reading

* [SwiftLint - First Where](https://realm.github.io/SwiftLint/first_where.html)