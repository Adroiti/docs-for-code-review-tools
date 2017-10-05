Pattern: Use of `Set.intersection(_:).isEmpty`

Issue: -

## Description

Prefer using `Set.isDisjoint(with:)` over `Set.intersection(_:).isEmpty`.

Examples of **correct** code:
```swift
_ = Set(syntaxKinds).isDisjoint(with: commentAndStringKindsSet)


let isObjc = !objcAttributes.isDisjoint(with: dictionary.enclosedSwiftAttributes)


_ = Set(syntaxKinds).intersection(commentAndStringKindsSet)


_ = !objcAttributes.intersection(dictionary.enclosedSwiftAttributes)

```
Examples of **incorrect** code:
```swift

_ = Set(syntaxKinds).↓intersection(commentAndStringKindsSet).isEmpty


let isObjc = !objcAttributes.↓intersection(dictionary.enclosedSwiftAttributes).isEmpty

```

## Further Reading

* [SwiftLint - Is Disjoint](https://github.com/realm/SwiftLint/blob/master/Rules.md#is-disjoint)