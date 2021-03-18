Pattern: Use of bridged Objective-C reference type

Issue: -

## Description

Prefer Swift value types to bridged Objective-C reference types.

Examples of **correct** code:

```swift
var array = Array<Int>()

var calendar: Calendar? = nil
```

Examples of **incorrect** code:

```swift
var array = NSArray()

var calendar: NSCalendar? = nil
```

## Further Reading

* [SwiftLint - Legacy Objective-C Reference Type](https://realm.github.io/SwiftLint/legacy_objc_type.html)