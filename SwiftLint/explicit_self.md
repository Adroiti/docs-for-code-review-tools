Pattern: Missing use of explicit `self.`

Issue: -

## Description

Instance variables and functions should be explicitly accessed with `self.`.

Examples of **correct** code:
```swift
struct A {
    func f1() {}
    func f2() {
        self.f1()
    }
}


struct A {
    let p1: Int
    func f1() {
        _ = self.p1
    }
}

```
Examples of **incorrect** code:
```swift

struct A {
    func f1() {}
    func f2() {
        ↓f1()
    }
}


struct A {
    let p1: Int
    func f1() {
        _ = ↓p1
    }
}

```

## Further Reading

* [SwiftLint - Explicit Self](https://github.com/realm/SwiftLint/blob/master/Rules.md#explicit-self)