Pattern: Trailing whitespace

Issue: -

## Description

Adding trailing whitespace can cause extra work for others editing the same file, when they merge, as can removing existing trailing whitespace. So: Don't introduce trailing whitespace. Remove it if you're already changing that line, or do it in a separate clean-up operation (preferably when no-one else is working on the file).

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

* [SwiftLint - Trailing Whitespace](https://realm.github.io/SwiftLint/trailing_whitespace.html)