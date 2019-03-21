Pattern: Implementing `==` for `NSObject`

Issue: -

## Description

`NSObject` already exposes an implementation of `==` that calls out to `isEqual`. Adding a new implementation of `==` to an `NSObject` subclass can lead to odd situations where `a == b` is `true`, but `(a as NSObject) == b` (or, equivalently `a.isEqual(b)`) is `false`.

Examples of **correct** code:

```swift
class AClass: NSObject {
}


@objc class AClass: SomeNSObjectSubclass {
}


class AClass: Equatable {
    static func ==(lhs: AClass, rhs: AClass) -> Bool {
        return true
    }


class AClass: NSObject {
    override func isEqual(_ object: Any?) -> Bool {
        return true
    }
}


@objc class AClass: SomeNSObjectSubclass {
    override func isEqual(_ object: Any?) -> Bool {
        return false
    }
}


class AClass: NSObject {
    func ==(lhs: AClass, rhs: AClass) -> Bool {
        return true
    }
}


class AClass: NSObject {
    static func ==(lhs: AClass, rhs: BClass) -> Bool {
        return true
    }
}


struct AStruct: Equatable {
    static func ==(lhs: AStruct, rhs: AStruct) -> Bool {
        return false
    }
}


enum AnEnum: Equatable {
    static func ==(lhs: AnEnum, rhs: AnEnum) -> Bool {
        return true
    }
}

```
Examples of **incorrect** code:
```swift

class AClass: NSObject {
    ↓static func ==(lhs: AClass, rhs: AClass) -> Bool {
        return false
    }
}


@objc class AClass: SomeOtherNSObjectSubclass {
    ↓static func ==(lhs: AClass, rhs: AClass) -> Bool {
        return true
    }
}


class AClass: NSObject, Equatable {
    ↓static func ==(lhs: AClass, rhs: AClass) -> Bool {
        return false
    }
}


class AClass: NSObject {
    override func isEqual(_ object: Any?) -> Bool {
        guard let other = object as? AClass else {
            return false
        }
        return true
    }

    ↓static func ==(lhs: AClass, rhs: AClass) -> Bool {
        return false
    }
}

```

## Further Reading

* [SwiftLint - NSObject Prefer isEqual](https://github.com/realm/SwiftLint/blob/master/Rules.md#nsobject-prefer-isequal)