Pattern: Missing use of implicit return

Issue: -

## Description

Prefer implicit returns in closures.

Examples of **correct** code:
```swift
foo.map { $0 + 1 }


foo.map({ $0 + 1 })


foo.map { value in value + 1 }


func foo() -> Int {
  return 0
}


if foo {
  return 0
}


var foo: Bool { return true }

```
Examples of **incorrect** code:
```swift

foo.map { value in
  ↓return value + 1
}


foo.map {
  ↓return $0 + 1
}

```

## Further Reading

* [SwiftLint - Implicit Return](https://realm.github.io/SwiftLint/implicit_return.html)