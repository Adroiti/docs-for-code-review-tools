Pattern: Too many function parameters

Issue: -

## Description

Number of function parameters should be low.

Examples of **correct** code:
```swift
init(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}


init (a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}


`init`(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}


init?(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}


init?<T>(a: T, b: Int, c: Int, d: Int, e: Int, f: Int) {}


init?<T: String>(a: T, b: Int, c: Int, d: Int, e: Int, f: Int) {}


func f2(p1: Int, p2: Int) { }


func f(a: Int, b: Int, c: Int, d: Int, x: Int = 42) {}


func f(a: [Int], b: Int, c: Int, d: Int, f: Int) -> [Int] {
let s = a.flatMap { $0 as? [String: Int] } ?? []}}


override func f(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}

```
Examples of **incorrect** code:
```swift

↓func f(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}


↓func initialValue(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}


↓func f(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int = 2, g: Int) {}


struct Foo {
init(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}
↓func bar(a: Int, b: Int, c: Int, d: Int, e: Int, f: Int) {}}

```

## Further Reading

* [SwiftLint - Function Parameter Count](https://github.com/realm/SwiftLint/blob/master/Rules.md#function-parameter-count)