Pattern: Unneeded parentheses in closure argument

Issue: -

## Description

Parentheses are not needed when declaring closure arguments.

Examples of **correct** code:
```swift
let foo = { (bar: Int) in }


let foo = { bar in }


let foo = { bar -> Bool in return true }

```
Examples of **incorrect** code:
```swift

call(arg: { ↓(bar) in })


let foo = { ↓(bar) -> Bool in return true }


foo.map { ($0, $0) }.forEach { ↓(x, y) in }


foo.bar { [weak self] ↓(x, y) in }

```

## Further Reading

* [SwiftLint - Unneeded Parentheses in Closure Argument](https://github.com/realm/SwiftLint/blob/master/Rules.md#unneeded-parentheses-in-closure-argument)