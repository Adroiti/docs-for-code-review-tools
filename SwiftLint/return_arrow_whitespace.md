Pattern: Malformed returning whitespace

Issue: -

## Description

Return arrow and return type should be separated by a single space or on a separate line.

Examples of **correct** code:
```swift
func abc() -> Int {}


func abc() -> [Int] {}


func abc() -> (Int, Int) {}


var abc = {(param: Int) -> Void in }


func abc() ->
    Int {}


func abc()
    -> Int {}

```
Examples of **incorrect** code:
```swift

func abc()↓->Int {}


func abc()↓->[Int] {}


func abc()↓->(Int, Int) {}


func abc()↓-> Int {}


func abc()↓ ->Int {}


func abc()↓  ->  Int {}


var abc = {(param: Int)↓ ->Bool in }


var abc = {(param: Int)↓->Bool in }

```

## Further Reading

* [SwiftLint - Returning Whitespace](https://realm.github.io/SwiftLint/return_arrow_whitespace.html)