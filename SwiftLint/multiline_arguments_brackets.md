Pattern: Malformed brackets for multi-line argument

Issue: -

## Description

Multi-line arguments should have their surrounding brackets in a new line.

Examples of **correct** code:
```swift
foo(param1: "Param1", param2: "Param2", param3: "Param3")


foo(
    param1: "Param1", param2: "Param2", param3: "Param3"
)


func foo(
    param1: "Param1",
    param2: "Param2",
    param3: "Param3"
)


foo { param1, param2 in
    print("hello world")
}


foo(
    bar(
        x: 5,
        y: 7
    )
)


AlertViewModel.AlertAction(title: "some title", style: .default) {
    AlertManager.shared.presentNextDebugAlert()
}

```
Examples of **incorrect** code:
```swift

foo(↓param1: "Param1", param2: "Param2",
         param3: "Param3"
)


foo(
    param1: "Param1",
    param2: "Param2",
    param3: "Param3"↓)


foo(↓bar(
    x: 5,
    y: 7
)
)


foo(
    bar(
        x: 5,
        y: 7
)↓)

```

## Further Reading

* [SwiftLint - Multiline Arguments Brackets](https://realm.github.io/SwiftLint/multiline_arguments_brackets.html)