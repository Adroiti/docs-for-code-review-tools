Pattern: Missing use of `isEmpty`

Issue: -

## Description

Prefer checking `isEmpty` over comparing collection to an empty array or dictionary literal.

Examples of **correct** code:

```swift
myArray = []


myArray.isEmpty


!myArray.isEmpy


myDict = [:]

```
Examples of **incorrect** code:

```swift

myArray↓ == []


myArray↓ != []


myArray↓ == [ ]


myDict↓ == [:]


myDict↓ != [:]


myDict↓ == [: ]


myDict↓ == [ :]


myDict↓ == [ : ]

```

## Further Reading

* [SwiftLint - Empty Collection Literal](https://github.com/realm/SwiftLint/blob/master/Rules.md#empty-collection-literal)