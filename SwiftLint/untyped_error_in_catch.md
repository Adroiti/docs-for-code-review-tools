Pattern: Untyped error in `catch`

Issue: -

## Description

Catch statements should not declare error variables without type casting.

Examples of **correct** code:
```swift
do {
    try foo() 
} catch {}


do {
    try foo() 
} catch Error.invalidOperation {
} catch {}


do {
    try foo() 
} catch let error as MyError {
} catch {}


do {
    try foo() 
} catch var error as MyError {
} catch {}

```
Examples of **incorrect** code:
```swift

do {
    try foo() 
} ↓catch var error {}


do {
    try foo() 
} ↓catch let error {}


do {
    try foo() 
} ↓catch let someError {}


do {
    try foo() 
} ↓catch var someError {}


do {
    try foo() 
} ↓catch let e {}


do {
    try foo() 
} ↓catch(let error) {}


do {
    try foo() 
} ↓catch (let error) {}

```

## Further Reading

* [SwiftLint - Untyped Error in Catch](https://realm.github.io/SwiftLint/untyped_error_in_catch.html)