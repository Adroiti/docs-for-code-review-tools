Pattern: Malformed brackets for multi-line literal

Issue: -

## Description

Multi-line literals should have their surrounding brackets in a new line.

Examples of **correct** code:
```swift
let trio = ["harry", "ronald", "hermione"]
let houseCup = ["gryffinder": 460, "hufflepuff": 370, "ravenclaw": 410, "slytherin": 450]


let trio = [
    "harry",
    "ronald",
    "hermione"
]
let houseCup = [
    "gryffinder": 460,
    "hufflepuff": 370,
    "ravenclaw": 410,
    "slytherin": 450
]


let trio = [
    "harry", "ronald", "hermione"
]
let houseCup = [
    "gryffinder": 460, "hufflepuff": 370,
    "ravenclaw": 410, "slytherin": 450
]


    _ = [
        1,
        2,
        3,
        4,
        5, 6,
        7, 8, 9
    ]

```
Examples of **incorrect** code:
```swift

let trio = [↓"harry",
            "ronald",
            "hermione"
]


let houseCup = [↓"gryffinder": 460, "hufflepuff": 370,
                "ravenclaw": 410, "slytherin": 450
]


let trio = [
    "harry",
    "ronald",
    "hermione"↓]


let houseCup = [
    "gryffinder": 460, "hufflepuff": 370,
    "ravenclaw": 410, "slytherin": 450↓]


class Hogwarts {
    let houseCup = [
        "gryffinder": 460, "hufflepuff": 370,
        "ravenclaw": 410, "slytherin": 450↓]
}


    _ = [
        1,
        2,
        3,
        4,
        5, 6,
        7, 8, 9↓]


    _ = [↓1, 2, 3,
         4, 5, 6,
         7, 8, 9
    ]

```

## Further Reading

* [SwiftLint - Multiline Literal Brackets](https://github.com/realm/SwiftLint/blob/master/Rules.md#multiline-literal-brackets)