Pattern: Unneeded `break` in `switch`

Issue: -

## Description

Avoid using unneeded `break` statements.

Examples of **correct** code:
```swift
switch foo {
case .bar:
    break
}


switch foo {
default:
    break
}


switch foo {
case .bar:
    for i in [0, 1, 2] { break }
}


switch foo {
case .bar:
    if true { break }
}


switch foo {
case .bar:
    something()
}

```
Examples of **incorrect** code:
```swift

switch foo {
case .bar:
    something()
    ↓break
}


switch foo {
case .bar:
    something()
    ↓break // comment
}


switch foo {
default:
    something()
    ↓break
}


switch foo {
case .foo, .foo2 where condition:
    something()
    ↓break
}

```

## Further Reading

* [SwiftLint - Unneeded Break in Switch](https://github.com/realm/SwiftLint/blob/master/Rules.md#unneeded-break-in-switch)