Pattern: Assigning variable through tuple pattern

Issue: -

## Description

Assigning variables through a tuple pattern (sometimes referred to as a tuple shuffle) is only permitted if the left-hand side of the assignment is unlabeled.

Labels on the left-hand side closely resemble type annotations, and can lead to confusing code.

Examples of **correct** code:
```swift
// ok
let (a, b) = (y: 4, x: 5.0)

// triggers

```
Examples of **incorrect** code:
```swift
let (x: a, y: b) = (y: 4, x: 5.0)
let (x: Int, y: Double) = (y: 4, x: 5.0)
```