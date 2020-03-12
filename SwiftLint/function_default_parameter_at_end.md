Pattern: Malformed location for parameter with default

Issue: -

## Description

Prefer to locate parameters with defaults toward the end of the parameter list.

Examples of **correct** code:
```swift
func foo(baz: String, bar: Int = 0) {}


func foo(x: String, y: Int = 0, z: CGFloat = 0) {}


func foo(bar: String, baz: Int = 0, z: () -> Void) {}


func foo(bar: String, z: () -> Void, baz: Int = 0) {}


func foo(bar: Int = 0) {}


func foo() {}


class A: B {
    override func foo(bar: Int = 0, baz: String) {}


func foo(bar: Int = 0, completion: @escaping CompletionHandler) {}


func foo(a: Int, b: CGFloat = 0) {
    let block = { (error: Error?) in }
}

```
Examples of **incorrect** code:
```swift

↓func foo(bar: Int = 0, baz: String) {}

```

## Further Reading

* [SwiftLint - Function Default Parameter at End](https://realm.github.io/SwiftLint/function_default_parameter_at_end.html)