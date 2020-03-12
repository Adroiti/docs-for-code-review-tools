Pattern: Operator declared as free function

Issue: -

## Description

Operators should be declared as static functions, not free functions.

Examples of **correct** code:
```swift
class A: Equatable {
  static func == (lhs: A, rhs: A) -> Bool {
    return false
  }


class A<T>: Equatable {
    static func == <T>(lhs: A<T>, rhs: A<T>) -> Bool {
        return false
    }


public extension Array where Element == Rule {
  static func == (lhs: Array, rhs: Array) -> Bool {
    if lhs.count != rhs.count { return false }
    return !zip(lhs, rhs).contains { !$0.0.isEqualTo($0.1) }
  }
}


private extension Optional where Wrapped: Comparable {
  static func < (lhs: Optional, rhs: Optional) -> Bool {
    switch (lhs, rhs) {
    case let (lhs?, rhs?):
      return lhs < rhs
    case (nil, _?):
      return true
    default:
      return false
    }
  }
}

```
Examples of **incorrect** code:
```swift

↓func == (lhs: A, rhs: A) -> Bool {
  return false
}


↓func == <T>(lhs: A<T>, rhs: A<T>) -> Bool {
  return false
}


↓func == (lhs: [Rule], rhs: [Rule]) -> Bool {
  if lhs.count != rhs.count { return false }
  return !zip(lhs, rhs).contains { !$0.0.isEqualTo($0.1) }
}


private ↓func < <T: Comparable>(lhs: T?, rhs: T?) -> Bool {
  switch (lhs, rhs) {
  case let (lhs?, rhs?):
    return lhs < rhs
  case (nil, _?):
    return true
  default:
    return false
  }
}

```

## Further Reading

* [SwiftLint - Static Operator](https://realm.github.io/SwiftLint/static_operator.html)