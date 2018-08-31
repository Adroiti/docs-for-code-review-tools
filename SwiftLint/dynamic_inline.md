Pattern: Use of `dynamic` and `@inline(__always)` 

Issue: -

## Description

When a class method is marked as both `dynamic` and `@inline(__always)`, its dispatch behavior is not well defined. Therefore this specific combination is discouraged.

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