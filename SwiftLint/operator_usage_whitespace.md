Pattern: Malformed whitespace around operator

Issue: -

## Description

Operators should be surrounded by a single whitespace when they are being used.

Examples of **correct** code:
```swift
let foo = 1 + 2


let foo = 1 > 2


let foo = !false


let foo: Int?


let foo: Array<String>


let foo: [String]


let foo = 1 + 
  2


let range = 1...3


let range = 1 ... 3


let range = 1..<3


#if swift(>=3.0)
    foo()
#endif


array.removeAtIndex(-200)


let name = "image-1"


button.setImage(#imageLiteral(resourceName: "image-1"), for: .normal)


let doubleValue = -9e-11

```
Examples of **incorrect** code:
```swift

let foo = 1↓+2


let foo = 1↓   + 2


let foo = 1↓   +    2


let foo = 1↓ +    2


let foo↓=1↓+2


let foo↓=1 + 2


let foo↓=bar


let range = 1↓ ..<  3


let foo = bar↓   ?? 0


let foo = bar↓??0


let foo = bar↓ !=  0


let foo = bar↓ !==  bar2


let v8 = Int8(1)↓  << 6


let v8 = 1↓ <<  (6)


let v8 = 1↓ <<  (6)
 let foo = 1 > 2

```

## Further Reading

* [SwiftLint - Operator Usage Whitespace](https://github.com/realm/SwiftLint/blob/master/Rules.md#operator-usage-whitespace)