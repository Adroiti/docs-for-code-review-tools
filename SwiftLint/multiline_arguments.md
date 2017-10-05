Pattern: Use of multi-line arguments

Issue: -

## Description

Arguments should be either on the same line, or one per line.

Examples of **correct** code:
```swift
foo()


foo(
    
)


foo { }


foo {
    
}


foo(0)


foo(0, 1)


foo(0, 1) { }


foo(0, param1: 1)


foo(0, param1: 1) { }


foo(param1: 1)


foo(param1: 1) { }


foo(param1: 1, param2: true) { }


foo(param1: 1, param2: true, param3: [3]) { }


foo(param1: 1, param2: true, param3: [3]) {
    bar()
}


foo(param1: 1,
    param2: true,
    param3: [3])


foo(
    param1: 1, param2: true, param3: [3]
)


foo(
    param1: 1,
    param2: true,
    param3: [3]
)

```
Examples of **incorrect** code:
```swift

foo(0,
    param1: 1, ↓param2: true, ↓param3: [3])


foo(0, ↓param1: 1,
    param2: true, ↓param3: [3])


foo(0, ↓param1: 1, ↓param2: true,
    param3: [3])


foo(
    0, ↓param1: 1,
    param2: true, ↓param3: [3]
)

```

## Further Reading

* [SwiftLint - Multiline Arguments](https://github.com/realm/SwiftLint/blob/master/Rules.md#multiline-arguments)