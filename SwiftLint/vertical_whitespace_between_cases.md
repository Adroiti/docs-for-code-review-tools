Pattern: Missing empty line between `switch` cases

Issue: -

## Description

Include a single empty line between `switch` cases.

Examples of **correct** code:
```swift
    switch x {
    case .valid:
        print("multiple ...")
        print("... lines")

    case .invalid:
        print("multiple ...")
        print("... lines")
    }


    switch x {
    case .valid:
        print("x is valid")

    case .invalid:
        print("x is invalid")
    }


    switch x {
    case 0..<5:
        print("x is valid")

    default:
        print("x is invalid")
    }


switch x {

case 0..<5:
    print("x is low")

case 5..<10:
    print("x is high")

default:
    print("x is invalid")

}


switch x {
case 0..<5:
    print("x is low")

case 5..<10:
    print("x is high")

default:
    print("x is invalid")
}


switch x {
case 0..<5: print("x is low")
case 5..<10: print("x is high")
default: print("x is invalid")
}


switch x {    
case 1:    
    print("one")    
    
default:    
    print("not one")    
}    

```
Examples of **incorrect** code:
```swift

    switch x {
    case .valid:
        print("multiple ...")
        print("... lines")
↓    case .invalid:
        print("multiple ...")
        print("... lines")
    }


    switch x {
    case .valid:
        print("x is valid")
↓    case .invalid:
        print("x is invalid")
    }


    switch x {
    case 0..<5:
        print("x is valid")
↓    default:
        print("x is invalid")
    }

```

## Further Reading

* [SwiftLint - Vertical Whitespace Between Cases](https://realm.github.io/SwiftLint/vertical_whitespace_between_cases.html)