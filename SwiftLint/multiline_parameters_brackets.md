Pattern: Malformed brackets for multi-line parameter

Issue: -

## Description

Multi-line parameters should have their surrounding brackets in a new line.

Examples of **correct** code:
```swift
func foo(param1: String, param2: String, param3: String)


func foo(
    param1: String, param2: String, param3: String
)


func foo(
    param1: String,
    param2: String,
    param3: String
)


class SomeType {
    func foo(param1: String, param2: String, param3: String)
}


class SomeType {
    func foo(
        param1: String, param2: String, param3: String
    )
}


class SomeType {
    func foo(
        param1: String,
        param2: String,
        param3: String
    )
}


func foo<T>(param1: T, param2: String, param3: String) -> T { /* some code */ }

```
Examples of **incorrect** code:
```swift

func foo(↓param1: String, param2: String,
         param3: String
)


func foo(
    param1: String,
    param2: String,
    param3: String↓)


class SomeType {
    func foo(↓param1: String, param2: String,
             param3: String
    )
}


class SomeType {
    func foo(
        param1: String,
        param2: String,
        param3: String↓)
}


func foo<T>(↓param1: T, param2: String,
         param3: String
) -> T

```

## Further Reading

* [SwiftLint - Multiline Parameters Brackets](https://realm.github.io/SwiftLint/multiline_parameters_brackets.html)