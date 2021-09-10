Pattern: Duplicated key in dictionary literal

Issue: -

## Description

Dictionary literals with duplicated keys will crash in runtime.

Examples of **correct** code:

```swift
[
	1: "1",
	2: "2"
]
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

* [SwiftLint - Duplicated Key in Dictionary Literal](https://realm.github.io/SwiftLint/duplicated_key_in_dictionary_literal.html)