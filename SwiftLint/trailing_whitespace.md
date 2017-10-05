Pattern: Trailing Whitespace

Issue: -

## Description

Lines should not have trailing whitespace.

Examples of **correct** code:

```swift
let name: String

//

// 

let name: String //

let name: String // 

```

Examples of **incorrect** code:

```swift

let name: String 

/* */ let name: String 

```

## Further Reading

* [SwiftLint - Trailing Whitespace](https://github.com/realm/SwiftLint/blob/master/Rules.md#trailing-whitespace)