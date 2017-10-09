Pattern: Malformed whitespace around `func`

Issue: -

## Description

Operators should be surrounded by a single whitespace when defining them.

Examples of **correct** code:
```swift
func <| (lhs: Int, rhs: Int) -> Int {}


func <|< <A>(lhs: A, rhs: A) -> A {}


func abc(lhs: Int, rhs: Int) -> Int {}

```
Examples of **incorrect** code:
```swift

↓func <|(lhs: Int, rhs: Int) -> Int {}


↓func <|<<A>(lhs: A, rhs: A) -> A {}


↓func <|  (lhs: Int, rhs: Int) -> Int {}


↓func <|<  <A>(lhs: A, rhs: A) -> A {}


↓func  <| (lhs: Int, rhs: Int) -> Int {}


↓func  <|< <A>(lhs: A, rhs: A) -> A {}

```

## Further Reading

* [SwiftLint - Operator Function Whitespace](https://github.com/realm/SwiftLint/blob/master/Rules.md#operator-function-whitespace)