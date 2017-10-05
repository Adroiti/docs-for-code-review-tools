Pattern: Malformed trailing `,`

Issue: -

## Description

Trailing commas in arrays and dictionaries should be avoided or enforced.

Examples of **correct** code:
```swift
let foo = [1, 2, 3]


let foo = []


let foo = [:]


let foo = [1: 2, 2: 3]


let foo = [Void]()


let example = [ 1,
 2
 // 3,
]


foo([1: "\(error)"])

```
Examples of **incorrect** code:
```swift

let foo = [1, 2, 3↓,]


let foo = [1, 2, 3↓, ]


let foo = [1, 2, 3   ↓,]


let foo = [1: 2, 2: 3↓, ]


struct Bar {
 let foo = [1: 2, 2: 3↓, ]
}


let foo = [1, 2, 3↓,] + [4, 5, 6↓,]


let example = [ 1,
2↓,
 // 3,
]


let foo = ["אבג", "αβγ", "🇺🇸"↓,]

```

## Further Reading

* [SwiftLint - Trailing Comma](https://github.com/realm/SwiftLint/blob/master/Rules.md#trailing-comma)