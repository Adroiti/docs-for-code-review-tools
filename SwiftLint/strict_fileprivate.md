Pattern: Use of `fileprivate`

Issue: -

## Description

`fileprivate` should be avoided.

Examples of **correct** code:
```swift
extension String {}


private extension String {}


public 
 extension String {}


open extension 
 String {}


internal extension String {}

```
Examples of **incorrect** code:
```swift

↓fileprivate extension String {}


↓fileprivate 
 extension String {}


↓fileprivate extension 
 String {}


extension String {
↓fileprivate func Something(){}
}


class MyClass {
↓fileprivate let myInt = 4
}


class MyClass {
↓fileprivate(set) var myInt = 4
}


struct Outter {
struct Inter {
↓fileprivate struct Inner {}
}
}

```

## Further Reading

* [SwiftLint - Strict fileprivate](https://realm.github.io/SwiftLint/strict_fileprivate.html)