Pattern: Missing use of `.allSatisfy()`/`.contains()`

Issue: -

## Description

Prefer using `.allSatisfy()` or `.contains()` over `reduce(true)` or `reduce(false)`

Examples of **correct** code:

```swift
nums.reduce(0) { $0.0 + $0.1 }


nums.reduce(0.0) { $0.0 + $0.1 }

```
Examples of **incorrect** code:

```swift

let allNines = nums.↓reduce(true) { $0.0 && $0.1 == 9 }


let anyNines = nums.↓reduce(false) { $0.0 || $0.1 == 9 }


let allValid = validators.↓reduce(true) { $0 && $1(input) }


let anyValid = validators.↓reduce(false) { $0 || $1(input) }


let allNines = nums.↓reduce(true, { $0.0 && $0.1 == 9 })


let anyNines = nums.↓reduce(false, { $0.0 || $0.1 == 9 })


let allValid = validators.↓reduce(true, { $0 && $1(input) })


let anyValid = validators.↓reduce(false, { $0 || $1(input) })

```

## Further Reading

* [SwiftLint - Reduce Boolean](https://github.com/realm/SwiftLint/blob/master/Rules.md#reduce-boolean)