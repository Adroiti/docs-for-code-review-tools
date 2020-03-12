Pattern: Discarded `NotificationCenter` observer

Issue: -

## Description

When registering for a notification using a block, the opaque observer that is returned should be stored so it can be removed later.

Examples of **correct** code:
```swift
let foo = nc.addObserver(forName: .NSSystemTimeZoneDidChange, object: nil, queue: nil) { }


let foo = nc.addObserver(forName: .NSSystemTimeZoneDidChange, object: nil, queue: nil, using: { })


func foo() -> Any {
   return nc.addObserver(forName: .NSSystemTimeZoneDidChange, object: nil, queue: nil, using: { })
}

```
Examples of **incorrect** code:
```swift

↓nc.addObserver(forName: .NSSystemTimeZoneDidChange, object: nil, queue: nil) { }


↓nc.addObserver(forName: .NSSystemTimeZoneDidChange, object: nil, queue: nil, using: { })


@discardableResult func foo() -> Any {
   return ↓nc.addObserver(forName: .NSSystemTimeZoneDidChange, object: nil, queue: nil, using: { })
}

```

## Further Reading

* [SwiftLint - Discarded Notification Center Observer](https://realm.github.io/SwiftLint/discarded_notification_center_observer.html)