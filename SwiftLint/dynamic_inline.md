Pattern: Use of `dynamic` and `@inline(__always)` 

Issue: -

## Description

Avoid using `dynamic` and `@inline(__always)` together.

Examples of **correct** code:
```swift
class C {
dynamic func f() {}}


class C {
@inline(__always) func f() {}}


class C {
@inline(never) dynamic func f() {}}

```
Examples of **incorrect** code:
```swift

class C {
@inline(__always) dynamic ↓func f() {}
}


class C {
@inline(__always) public dynamic ↓func f() {}
}


class C {
@inline(__always) dynamic internal ↓func f() {}
}


class C {
@inline(__always)
dynamic ↓func f() {}
}


class C {
@inline(__always)
dynamic
↓func f() {}
}

```

## Further Reading

* [SwiftLint - Dynamic Inline](https://github.com/realm/SwiftLint/blob/master/Rules.md#dynamic-inline)