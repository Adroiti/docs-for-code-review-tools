Pattern: Use of `fileprivate` declaration

Issue: -

## Description

Prefer `private` over `fileprivate` declarations. 

Examples of **correct** code:
```swift
extension String {}


private extension String {}


public 
 enum MyEnum {}


open extension 
 String {}


internal extension String {}


extension String {
fileprivate func Something(){}
}


class MyClass {
fileprivate let myInt = 4
}


class MyClass {
fileprivate(set) var myInt = 4
}


struct Outter {
struct Inter {
fileprivate struct Inner {}
}
}

```
Examples of **incorrect** code:
```swift

↓fileprivate enum MyEnum {}


↓fileprivate class MyClass {
fileprivate(set) var myInt = 4
}

```

## Further Reading

* [SwiftLint - Private over fileprivate](https://github.com/realm/SwiftLint/blob/master/Rules.md#private-over-fileprivate)