Pattern: Use of `-> ()`

Issue: -

## Description

Prefer `-> Void` over `-> ()`.

Examples of **correct** code:
```swift
let abc: () -> Void = {}


let abc: () -> (VoidVoid) = {}


func foo(completion: () -> Void)


let foo: (ConfigurationTests) -> () throws -> Void)


let foo: (ConfigurationTests) ->   () throws -> Void)


let foo: (ConfigurationTests) ->() throws -> Void)


let foo: (ConfigurationTests) -> () -> Void)

```
Examples of **incorrect** code:
```swift

let abc: () -> ↓() = {}


let abc: () -> ↓(Void) = {}


let abc: () -> ↓(   Void ) = {}


func foo(completion: () -> ↓())


func foo(completion: () -> ↓(   ))


func foo(completion: () -> ↓(Void))


let foo: (ConfigurationTests) -> () throws -> ↓())

```

## Further Reading

* [SwiftLint - Void Return](https://github.com/realm/SwiftLint/blob/master/Rules.md#void-return)