Pattern: Tuple has too many members

Issue: -

## Description

Tuples shouldn't have too many members. Create a custom type instead.

Examples of **correct** code:
```swift
let foo: (Int, Int)


let foo: (start: Int, end: Int)


let foo: (Int, (Int, String))


func foo() -> (Int, Int)


func foo() -> (Int, Int) {}


func foo(bar: String) -> (Int, Int)


func foo(bar: String) -> (Int, Int) {}


func foo() throws -> (Int, Int)


func foo() throws -> (Int, Int) {}


let foo: (Int, Int, Int) -> Void


let foo: (Int, Int, Int) throws -> Void


func foo(bar: (Int, String, Float) -> Void)


func foo(bar: (Int, String, Float) throws -> Void)


var completionHandler: ((_ data: Data?, _ resp: URLResponse?, _ e: NSError?) -> Void)!


func getDictionaryAndInt() -> (Dictionary<Int, String>, Int)?


func getGenericTypeAndInt() -> (Type<Int, String, Float>, Int)?

```
Examples of **incorrect** code:
```swift

↓let foo: (Int, Int, Int)


↓let foo: (start: Int, end: Int, value: String)


↓let foo: (Int, (Int, Int, Int))


func foo(↓bar: (Int, Int, Int))


func foo() -> ↓(Int, Int, Int)


func foo() -> ↓(Int, Int, Int) {}


func foo(bar: String) -> ↓(Int, Int, Int)


func foo(bar: String) -> ↓(Int, Int, Int) {}


func foo() throws -> ↓(Int, Int, Int)


func foo() throws -> ↓(Int, Int, Int) {}


func foo() throws -> ↓(Int, ↓(String, String, String), Int) {}


func getDictionaryAndInt() -> (Dictionary<Int, ↓(String, String, String)>, Int)?

```

## Further Reading

* [SwiftLint - Large Tuple](https://github.com/realm/SwiftLint/blob/master/Rules.md#large-tuple)