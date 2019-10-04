Pattern: Use of `map` instead of `flatMap`

Issue: -

## Description

Prefer `flatMap` over `map` followed by `reduce([], +)`.

Examples of **correct** code:

```swift
let foo = bar.map { $0.count }.reduce(0, +)


let foo = bar.flatMap { $0.array }

```

Examples of **incorrect** code:

```swift

let foo = ↓bar.map { $0.array }.reduce([], +)

```

## Further Reading

* [SwiftLint - FlatMap over map and reduce](https://github.com/realm/SwiftLint/blob/master/Rules.md#flatmap-over-map-and-reduce)