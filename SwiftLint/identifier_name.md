Pattern: Invalid identifier name

Issue: -

## Description

Identifier names should only contain alphanumeric characters and start with a lowercase character or should only contain capital letters. In an exception to the above, variable names may start with a capital letter when they are declared static and immutable. Variable names should not be too long or too short.

Examples of **correct** code:
```swift
let myLet = 0


var myVar = 0


private let _myLet = 0


class Abc { static let MyLet = 0 }


let URL: NSURL? = nil


let XMLString: String? = nil


override var i = 0


enum Foo { case myEnum }


func isOperator(name: String) -> Bool


func typeForKind(_ kind: SwiftDeclarationKind) -> String


func == (lhs: SyntaxToken, rhs: SyntaxToken) -> Bool


override func IsOperator(name: String) -> Bool

```
Examples of **incorrect** code:
```swift

↓let MyLet = 0


↓let _myLet = 0


private ↓let myLet_ = 0


↓let myExtremelyVeryVeryVeryVeryVeryVeryLongLet = 0


↓var myExtremelyVeryVeryVeryVeryVeryVeryLongVar = 0


private ↓let _myExtremelyVeryVeryVeryVeryVeryVeryLongLet = 0


↓let i = 0


↓var id = 0


private ↓let _i = 0


↓func IsOperator(name: String) -> Bool


enum Foo { case ↓MyEnum }

```

## Further Reading

* [SwiftLint - Identifier Name](https://github.com/realm/SwiftLint/blob/master/Rules.md#identifier-name)