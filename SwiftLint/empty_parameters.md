Pattern: Use of `Void -> `

Issue: -

## Description

Prefer `() -> ` over `Void -> `.

Examples of **correct** code:
```swift
let abc: () -> Void = {}


func foo(completion: () -> Void)


func foo(completion: () thows -> Void)


let foo: (ConfigurationTests) -> Void throws -> Void)


let foo: (ConfigurationTests) ->   Void throws -> Void)


let foo: (ConfigurationTests) ->Void throws -> Void)

```
Examples of **incorrect** code:
```swift

let abc: ↓(Void) -> Void = {}


func foo(completion: ↓(Void) -> Void)


func foo(completion: ↓(Void) throws -> Void)


let foo: ↓(Void) -> () throws -> Void)

```

## Further Reading

* [SwiftLint - Empty Parameters](https://github.com/realm/SwiftLint/blob/master/Rules.md#empty-parameters)