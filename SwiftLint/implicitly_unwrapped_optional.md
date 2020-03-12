Pattern: Use of implicitly unwrapped optional

Issue: -

## Description

Implicitly unwrapped optionals should be avoided when possible.

Examples of **correct** code:
```swift
@IBOutlet private var label: UILabel!


@IBOutlet var label: UILabel!


@IBOutlet var label: [UILabel!]


if !boolean {}


let int: Int? = 42


let int: Int? = nil

```
Examples of **incorrect** code:
```swift

let label: UILabel!


let IBOutlet: UILabel!


let labels: [UILabel!]


var ints: [Int!] = [42, nil, 42]


let label: IBOutlet!


let int: Int! = 42


let int: Int! = nil


var int: Int! = 42


let int: ImplicitlyUnwrappedOptional<Int>


let collection: AnyCollection<Int!>


func foo(int: Int!) {}

```

## Further Reading

* [SwiftLint - Implicitly Unwrapped Optional](https://realm.github.io/SwiftLint/implicitly_unwrapped_optional.html)