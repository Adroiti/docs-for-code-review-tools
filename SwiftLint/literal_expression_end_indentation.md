Pattern: Malformed literal expression end indentation

Issue: -

## Description

Array and dictionary literal end should have the same indentation as the line that started it.

Examples of **correct** code:
```swift
[1, 2, 3]


[1,
 2
]


[
   1,
   2
]


[
   1,
   2]


   let x = [
       1,
       2
   ]


[key: 2, key2: 3]


[key: 1,
 key2: 2
]


[
   key: 0,
   key2: 20
]

```
Examples of **incorrect** code:
```swift

let x = [
   1,
   2
   ↓]


   let x = [
       1,
       2
↓]


let x = [
   key: value
   ↓]

```

## Further Reading

* [SwiftLint - Literal Expression End Indentation](https://realm.github.io/SwiftLint/literal_expression_end_indentation.html)