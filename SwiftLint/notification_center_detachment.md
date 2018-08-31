Pattern: Unsafe `NotificationCenter` detachment

Issue: -

## Description

Warns when an object removes itself as an observer to all notifications. This can be a problem if a superclass or a subclass wants to keep observing some notifications.

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

* [Big Nerd Ranch - Over-aggressive Unregistration](https://www.bignerdranch.com/blog/notifications-part-3-gotchas/#over-aggressive-unregistration)
* [SwiftLint - Notification Center Detachment](https://github.com/realm/SwiftLint/blob/master/Rules.md#notification-center-detachment)