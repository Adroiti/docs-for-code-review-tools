Pattern: Missing prefix for top-level constant

Issue: -

## Description

Top-level constants should be prefixed by `k`.

Examples of **correct** code:
```swift
private let kFoo = 20.0


public let kFoo = false


internal let kFoo = "Foo"


let kFoo = true


struct Foo {
   let bar = 20.0
}


private var foo = 20.0


public var foo = false


internal var foo = "Foo"


var foo = true


var foo = true, bar = true


var foo = true, let kFoo = true


let
   kFoo = true


var foo: Int {
   return a + b
}


let kFoo = {
   return a + b
}()

```
Examples of **incorrect** code:
```swift

private let ↓Foo = 20.0


public let ↓Foo = false


internal let ↓Foo = "Foo"


let ↓Foo = true


let ↓foo = 2, ↓bar = true


var foo = true, let ↓Foo = true


let
    ↓foo = true


let ↓foo = {
   return a + b
}()

```

## Further Reading

* [SwiftLint - Prefixed Top-Level Constant](https://github.com/realm/SwiftLint/blob/master/Rules.md#prefixed-top-level-constant)