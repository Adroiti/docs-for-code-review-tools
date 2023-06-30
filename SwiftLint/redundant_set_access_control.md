Pattern: Redundant access level for property setter

Issue: -

## Description

Property setter access level shouldn't be explicit if it's the same as the variable access level.

Examples of **correct** code:
```swift
private(set) public var foo: Int


public let foo: Int


public var foo: Int


var foo: Int


private final class A {
    private(set) var value: Int
}

```
Examples of **incorrect** code:
```swift

↓private(set) private var foo: Int


↓fileprivate(set) fileprivate var foo: Int


↓internal(set) internal var foo: Int


↓public(set) public var foo: Int


open class Foo {
    ↓open(set) open var bar: Int
}


class A {
    ↓internal(set) var value: Int
}


fileprivate class A {
    ↓fileprivate(set) var value: Int
}

```
