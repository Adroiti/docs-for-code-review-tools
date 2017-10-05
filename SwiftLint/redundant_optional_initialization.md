Pattern: Redundant optional initialization

Issue: -

## Description

Initializing an optional variable with `nil` is redundant.

Examples of **correct** code:
```swift
var myVar: Int?


let myVar: Int? = nil


var myVar: Int? = 0


func foo(bar: Int? = 0) { }


var myVar: Optional<Int>


let myVar: Optional<Int> = nil


var myVar: Optional<Int> = 0


var foo: Int? {
   if bar != nil { }
   return 0
}


var foo: Int? = {
   if bar != nil { }
   return 0
}()


lazy var test: Int? = nil

```
Examples of **incorrect** code:
```swift

var myVar: Int?↓ = nil


var myVar: Optional<Int>↓ = nil


var myVar: Int?↓=nil


var myVar: Optional<Int>↓=nil

```

## Further Reading

* [SwiftLint - Redundant Optional Initialization](https://github.com/realm/SwiftLint/blob/master/Rules.md#redundant-optional-initialization)