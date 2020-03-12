Pattern: Missing use of block based _KVO_ API

Issue: -

## Description

Prefer the new block based _KVO_ API with keypaths when using Swift 3.2 or later.

Examples of **correct** code:
```swift
let observer = foo.observe(\.value, options: [.new]) { (foo, change) in
   print(change.newValue)
}

```
Examples of **incorrect** code:
```swift

class Foo: NSObject {
   override ↓func observeValue(forKeyPath keyPath: String?, of object: Any?,
                               change: [NSKeyValueChangeKey : Any]?,
                               context: UnsafeMutableRawPointer?) {}
}


class Foo: NSObject {
   override ↓func observeValue(forKeyPath keyPath: String?, of object: Any?,
                               change: Dictionary<NSKeyValueChangeKey, Any>?,
                               context: UnsafeMutableRawPointer?) {}
}

```

## Further Reading

* [SwiftLint - Block Based KVO](https://realm.github.io/SwiftLint/block_based_kvo.html)