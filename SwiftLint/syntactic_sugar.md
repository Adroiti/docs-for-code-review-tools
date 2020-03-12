Pattern: Unused syntactic sugar

Issue: -

## Description

Shorthand syntactic sugar should be used, i.e. [Int] instead of `Array<Int>`.

Examples of **correct** code:
```swift
let x: [Int]


let x: [Int: String]


let x: Int?


func x(a: [Int], b: Int) -> [Int: Any]


let x: Int!


extension Array { 
 func x() { } 
 }


extension Dictionary { 
 func x() { } 
 }


let x: CustomArray<String>


var currentIndex: Array<OnboardingPage>.Index?


func x(a: [Int], b: Int) -> Array<Int>.Index


unsafeBitCast(nonOptionalT, to: Optional<T>.self)


type is Optional<String>.Type


let x: Foo.Optional<String>

```
Examples of **incorrect** code:
```swift

let x: ↓Array<String>


let x: ↓Dictionary<Int, String>


let x: ↓Optional<Int>


let x: ↓ImplicitlyUnwrappedOptional<Int>


func x(a: ↓Array<Int>, b: Int) -> [Int: Any]


func x(a: [Int], b: Int) -> ↓Dictionary<Int, String>


func x(a: ↓Array<Int>, b: Int) -> ↓Dictionary<Int, String>


let x = ↓Array<String>.array(of: object)


let x: ↓Swift.Optional<String>

```

## Further Reading

* [SwiftLint - Syntactic Sugar](https://realm.github.io/SwiftLint/syntactic_sugar.html)