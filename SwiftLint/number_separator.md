Pattern: Malformed thousand separator

Issue: -

## Description

Underscores should be used as thousand separator in large decimal numbers.

Examples of **correct** code:
```swift
let foo = -100


let foo = -1_000


let foo = -1_000_000


let foo = -1.000_1


let foo = -1_000_000.000_000_1


let binary = -0b10000


let binary = -0b1000_0001


let hex = -0xA


let hex = -0xAA_BB


let octal = -0o21


let octal = -0o21_1


let exp = -1_000_000.000_000e2


let foo = +100


let foo = +1_000


let foo = +1_000_000


let foo = +1.000_1


let foo = +1_000_000.000_000_1


let binary = +0b10000


let binary = +0b1000_0001


let hex = +0xA


let hex = +0xAA_BB


let octal = +0o21


let octal = +0o21_1


let exp = +1_000_000.000_000e2


let foo = 100


let foo = 1_000


let foo = 1_000_000


let foo = 1.000_1


let foo = 1_000_000.000_000_1


let binary = 0b10000


let binary = 0b1000_0001


let hex = 0xA


let hex = 0xAA_BB


let octal = 0o21


let octal = 0o21_1


let exp = 1_000_000.000_000e2

```
Examples of **incorrect** code:
```swift

let foo = ↓-10_0


let foo = ↓-1000


let foo = ↓-1000e2


let foo = ↓-1000E2


let foo = ↓-1__000


let foo = ↓-1.0001


let foo = ↓-1_000_000.000000_1


let foo = ↓-1000000.000000_1


let foo = +↓10_0


let foo = +↓1000


let foo = +↓1000e2


let foo = +↓1000E2


let foo = +↓1__000


let foo = +↓1.0001


let foo = +↓1_000_000.000000_1


let foo = +↓1000000.000000_1


let foo = ↓10_0


let foo = ↓1000


let foo = ↓1000e2


let foo = ↓1000E2


let foo = ↓1__000


let foo = ↓1.0001


let foo = ↓1_000_000.000000_1


let foo = ↓1000000.000000_1

```

## Further Reading

* [SwiftLint - Number Separator](https://github.com/realm/SwiftLint/blob/master/Rules.md#number-separator)