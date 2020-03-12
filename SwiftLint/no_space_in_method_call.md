Pattern: Space between method name and `()`

Issue: -

## Description

Don't add a space between the method name and the parentheses.

Examples of **correct** code:

```swift
foo()


object.foo()


object.foo(1)


object.foo(value: 1)


object.foo { print($0 }


list.sorted { $0.0 < $1.0 }.map { $0.value }


self.init(rgb: (Int) (colorInt))

```
Examples of **incorrect** code:

```swift

foo↓ ()


object.foo↓ ()


object.foo↓ (1)


object.foo↓ (value: 1)


object.foo↓ () {}


object.foo↓     ()

```

## Further Reading

* [SwiftLint - No Space in Method Call](https://realm.github.io/SwiftLint/no_space_in_method_call.html)