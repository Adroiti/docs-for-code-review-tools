Pattern: Redundant enum argument

Issue: -

## Description

Arguments can be omitted when matching enums with associated types if they are not used.

Examples of **correct** code:
```swift
switch foo {
    case .bar: break
}


switch foo {
    case .bar(let x): break
}


switch foo {
    case let .bar(x): break
}


switch (foo, bar) {
    case (_, _): break
}


switch foo {
    case "bar".uppercased(): break
}


switch (foo, bar) {
    case (_, _) where !something: break
}

```
Examples of **incorrect** code:
```swift

switch foo {
    case .bar↓(_): break
}


switch foo {
    case .bar↓(): break
}


switch foo {
    case .bar↓(_), .bar2↓(_): break
}


switch foo {
    case .bar↓() where method() > 2: break
}

```

## Further Reading

* [SwiftLint - Empty Enum Arguments](https://realm.github.io/SwiftLint/empty_enum_arguments.html)