Pattern: Malformed spacing around `,`

Issue: -

## Description

There should be no space before and one after any comma.

Examples of **correct** code:
```swift
func abc(a: String, b: String) { }


abc(a: "string", b: "string"


enum a { case a, b, c }


func abc(
  a: String,  // comment
  bcd: String // comment
) {
}


func abc(
  a: String,
  bcd: String
) {
}


#imageLiteral(resourceName: "foo,bar,baz")

```
Examples of **incorrect** code:
```swift

func abc(a: String↓ ,b: String) { }


func abc(a: String↓ ,b: String↓ ,c: String↓ ,d: String) { }


abc(a: "string"↓,b: "string"


enum a { case a↓ ,b }


let result = plus(
    first: 3↓ , // #683
    second: 4
)

```

## Further Reading

* [SwiftLint - Comma Spacing](https://github.com/realm/SwiftLint/blob/master/Rules.md#comma-spacing)