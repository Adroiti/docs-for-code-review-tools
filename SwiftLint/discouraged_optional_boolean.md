Pattern: Use of optional boolean

Issue: -

## Description

Prefer non-optional booleans over optional booleans.

Examples of **correct** code:
```swift
var foo: Bool


var foo: [String: Bool]


var foo: [Bool]


let foo: Bool = true


let foo: Bool = false

```
Examples of **incorrect** code:
```swift

var foo: ↓Bool?


var foo: [String: ↓Bool?]


var foo: [↓Bool?]


let foo: ↓Bool? = nil


let foo: [String: ↓Bool?] = [:]

```

## Further Reading

* [SwiftLint - Discouraged Optional Boolean](https://github.com/realm/SwiftLint/blob/master/Rules.md#discouraged-optional-boolean)