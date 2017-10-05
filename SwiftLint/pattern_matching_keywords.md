Pattern: Unmerged pattern matching bindings

Issue: -

## Description

Combine multiple pattern matching bindings by moving keywords out of tuples.

Examples of **correct** code:
```swift
switch foo {
    default: break
}


switch foo {
    case 1: break
}


switch foo {
    case bar: break
}


switch foo {
    case let (x, y): break
}


switch foo {
    case .foo(let x): break
}


switch foo {
    case let .foo(x, y): break
}


switch foo {
    case .foo(let x), .bar(let x): break
}


switch foo {
    case .foo(let x, var y): break
}


switch foo {
    case var (x, y): break
}


switch foo {
    case .foo(var x): break
}


switch foo {
    case var .foo(x, y): break
}

```
Examples of **incorrect** code:
```swift

switch foo {
    case (↓let x,  ↓let y): break
}


switch foo {
    case .foo(↓let x, ↓let y): break
}


switch foo {
    case (.yamlParsing(↓let x), .yamlParsing(↓let y)): break
}


switch foo {
    case (↓var x,  ↓var y): break
}


switch foo {
    case .foo(↓var x, ↓var y): break
}


switch foo {
    case (.yamlParsing(↓var x), .yamlParsing(↓var y)): break
}

```

## Further Reading

* [SwiftLint - Pattern Matching Keywords](https://github.com/realm/SwiftLint/blob/master/Rules.md#pattern-matching-keywords)