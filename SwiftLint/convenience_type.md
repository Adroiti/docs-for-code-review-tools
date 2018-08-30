Pattern: Missing use of enum to avoid instantiation

Issue: -

## Description

Types used for hosting only static members should be implemented as a caseless enum to avoid instantiation.

Examples of **correct** code:
```swift
enum Math { // enum
    public static let pi = 3.14
}


// class with inheritance
class MathViewController: UIViewController {
    public static let pi = 3.14
}


@objc class Math: NSObject { // class visible to Obj-C
    public static let pi = 3.14
}


struct Math { // type with non-static declarations
    public static let pi = 3.14
    public let randomNumber = 2
}


class DummyClass {}

```
Examples of **incorrect** code:
```swift

↓struct Math {
    public static let pi = 3.14
}


↓class Math {
    public static let pi = 3.14
}


↓struct Math {
    public static let pi = 3.14
    @available(*, unavailable) init() {}
}

```

## Further Reading

* [SwiftLint - Convenience Type](https://github.com/realm/SwiftLint/blob/master/Rules.md#convenience-type)