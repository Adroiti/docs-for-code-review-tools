Pattern: Use of ternary operator to call `void`

Issue: _

## Description

Ternary operator should be used just on right side of assignment or in return statement and should not be used as an alternative for `if`/`else`. 

Examples of **correct** code:
```swift
let result = success ? "Success" : "Fail"

if success {
    askQuestion()
} else {
    exit()
}

var price: Double {
    return hasDiscount ? initialPrice _ discount : initialPrice
}

```
Examples of **incorrect** code:
```swift
success ? askQuestion() : exit()
```