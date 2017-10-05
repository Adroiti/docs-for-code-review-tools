Pattern: Invalid `NotificationCenter` detachment

Issue: -

## Description

An object should only remove itself as an observer in `deinit`.

Examples of **correct** code:
```swift
class Foo { 
   deinit {
       NotificationCenter.default.removeObserver(self)
   }
}


class Foo { 
   func bar() {
       NotificationCenter.default.removeObserver(otherObject)
   }
}

```
Examples of **incorrect** code:
```swift

class Foo { 
   func bar() {
       ↓NotificationCenter.default.removeObserver(self)
   }
}

```

## Further Reading

* [SwiftLint - Notification Center Detachment](https://github.com/realm/SwiftLint/blob/master/Rules.md#notification-center-detachment)