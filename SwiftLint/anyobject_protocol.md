Pattern: Use of `class` instead of `AnyObject`

Issue: -

## Description

Prefer using `AnyObject` over `class` for class-only protocols.

Examples of **correct** code:
```swift
protocol SomeProtocol {}


protocol SomeClassOnlyProtocol: AnyObject {}


protocol SomeClassOnlyProtocol: AnyObject, SomeInheritedProtocol {}


@objc protocol SomeClassOnlyProtocol: AnyObject, SomeInheritedProtocol {}

```
Examples of **incorrect** code:
```swift

protocol SomeClassOnlyProtocol: ↓class {}


protocol SomeClassOnlyProtocol: ↓class, SomeInheritedProtocol {}


@objc protocol SomeClassOnlyProtocol: ↓class, SomeInheritedProtocol {}

```

## Further Reading

* [SwiftLint - AnyObject Protocol](https://github.com/realm/SwiftLint/blob/master/Rules.md#anyobject-protocol)