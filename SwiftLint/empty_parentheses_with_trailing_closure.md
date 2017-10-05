Pattern: Empty parentheses with trailing closure

Issue: -

## Description

When using trailing closures, empty parentheses should be avoided after the method call.

Examples of **correct** code:
```swift
[1, 2].map { $0 + 1 }


[1, 2].map({ $0 + 1 })


[1, 2].reduce(0) { $0 + $1 }


[1, 2].map { number in
 number + 1 
}


let isEmpty = [1, 2].isEmpty()


UIView.animateWithDuration(0.3, animations: {
   self.disableInteractionRightView.alpha = 0
}, completion: { _ in
   ()
})

```
Examples of **incorrect** code:
```swift

[1, 2].map↓() { $0 + 1 }


[1, 2].map↓( ) { $0 + 1 }


[1, 2].map↓() { number in
 number + 1 
}


[1, 2].map↓(  ) { number in
 number + 1 
}

```

## Further Reading

* [SwiftLint - Empty Parentheses with Trailing Closure](https://github.com/realm/SwiftLint/blob/master/Rules.md#empty-parentheses-with-trailing-closure)