Pattern: Malformed whitespace

Issue: -

## Description

Don't use blank lines when you don't have to. In particular, don't put more than one or two blank lines between functions, resist starting functions with a blank line, don't end functions with a blank line, and be discriminating with your use of blank lines inside functions.

The basic principle is: The more code that fits on one screen, the easier it is to follow and understand the control flow of the program. Of course, readability can suffer from code being too dense as well as too spread out, so use your judgment. But in general, minimize use of vertical whitespace.

Examples of **correct** code:
```swift
let abc = 0


let abc = 0


/* bcs 


*/


// bca 

```
Examples of **incorrect** code:
```swift

let aaaa = 0



struct AAAA {}



class BBBB {}

```

## Further Reading

* [SwiftLint - Vertical Whitespace](https://realm.github.io/SwiftLint/vertical_whitespace.html)