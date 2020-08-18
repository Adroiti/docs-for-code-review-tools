Pattern: Unneeded `NotificationCenter` removal

Issue: -

## Description

Observers are automatically unregistered on dealloc (iOS 9 / macOS 10.11) so you should’t call `removeObserver(self)` in the deinit.

Examples of **correct** code:

```swift
class Example {
    deinit {
        NotificationCenter.default.removeObserver(someOtherObserver)
    }
}
class Example {
    func removeObservers() {
        NotificationCenter.default.removeObserver(self)
    }
}
class Example {
    deinit {
        cleanup()
    }
}
```

Examples of **incorrect** code:

```swift
class Foo {
    deinit {
        NotificationCenter.default.removeObserver(↓self)
    }
}
class Foo {
    deinit {
        NotificationCenter.default.removeObserver(↓self,
                                                  name: UITextView.textDidChangeNotification, object: nil)
    }
}
```

## Further Reading

* [SwiftLint - Unneeded NotificationCenter Removal](https://realm.github.io/SwiftLint/unneeded_notification_center_removal.html)