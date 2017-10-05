Pattern: Misaligned `switch` and `case`

Issue: -

## Description

`case` statements should vertically align with the enclosing `switch` statement.

Examples of **correct** code:
```swift
switch someBool {
case true: // case 1
    print('red')
case false:
    /*
    case 2
    */
    if case let .someEnum(val) = someFunc() {
        print('blue')
    }
}
enum SomeEnum {
    case innocent
}


if aBool {
    switch someBool {
    case true:
        print('red')
    case false:
        print('blue')
    }
}


switch someInt {
// comments ignored
case 0:
    // zero case
    print('Zero')
case 1:
    print('One')
default:
    print('Some other number')
}

```
Examples of **incorrect** code:
```swift

switch someBool {
    ↓case true:
         print('red')
    ↓case false:
         print('blue')
}


if aBool {
    switch someBool {
        ↓case true:
            print('red')
    case false:
        print('blue')
    }
}


switch someInt {
    ↓case 0:
    print('Zero')
case 1:
    print('One')
    ↓default:
    print('Some other number')
}

```

## Further Reading

* [SwiftLint - Switch and Case Statement Alignment](https://github.com/realm/SwiftLint/blob/master/Rules.md#switch-and-case-statement-alignment)