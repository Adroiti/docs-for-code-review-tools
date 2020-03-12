Pattern: Unused control flow label

Issue: -

## Description

Unused control flow label should be removed.

Examples of **correct** code:
```swift
loop: while true { break loop }


loop: while true { continue loop }


loop:
    while true { break loop }


while true { break }


loop: for x in array { break loop }


label: switch number {
case 1: print("1")
case 2: print("2")
default: break label
}


loop: repeat {
    if x == 10 {
        break loop
    }
} while true

```
Examples of **incorrect** code:
```swift

↓loop: while true { break }


↓loop: while true { break loop1 }


↓loop: while true { break outerLoop }


↓loop: for x in array { break }


↓label: switch number {
case 1: print("1")
case 2: print("2")
default: break
}


↓loop: repeat {
    if x == 10 {
        break
    }
} while true

```

## Further Reading

* [SwiftLint - Unused Control Flow Label](https://realm.github.io/SwiftLint/unused_control_flow_label.html)