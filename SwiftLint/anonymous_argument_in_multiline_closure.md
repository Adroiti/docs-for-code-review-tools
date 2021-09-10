Pattern: Anonymous argument in multiline closure

Issue: -

## Description

Use named arguments in multiline closures.

Examples of **correct** code:

```swift
closure { $0 }
```

Examples of **incorrect** code:
```swift
[
	1: "1",
	2: "2",
	↓1: "one"
]
```

## Further Reading

* [SwiftLint - Anonymous Argument in Multiline Closure](https://realm.github.io/SwiftLint/anonymous_argument_in_multiline_closure.html)