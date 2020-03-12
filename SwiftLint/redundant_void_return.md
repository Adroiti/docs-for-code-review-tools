Pattern: Redundant `Void` return

Issue: -

## Description

Returning `Void` in a function declaration is redundant.

Examples of **correct** code:
```swift
func foo() {}


func foo() -> Int {}


func foo() -> Int -> Void {}


func foo() -> VoidResponse


let foo: Int -> Void


func foo() -> Int -> () {}


let foo: Int -> ()


func foo() -> ()?


func foo() -> ()!


func foo() -> Void?


func foo() -> Void!

```
Examples of **incorrect** code:
```swift

func foo()↓ -> Void {}


protocol Foo {
 func foo()↓ -> Void
}


func foo()↓ -> () {}


protocol Foo {
 func foo()↓ -> ()
}

```

## Further Reading

* [SwiftLint - Redundant Void Return](https://realm.github.io/SwiftLint/redundant_void_return.html)