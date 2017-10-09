Pattern: Dangerous type initialization

Issue: -

## Description

Discouraged direct initialization of types that can be harmful.

Examples of **correct** code:
```swift
let foo = UIDevice.current


let foo = Bundle.main


let foo = Bundle(path: "bar")


let foo = Bundle(identifier: "bar")


let foo = Bundle.init(path: "bar")


let foo = Bundle.init(identifier: "bar")

```
Examples of **incorrect** code:
```swift

↓UIDevice()


↓Bundle()


let foo = ↓UIDevice()


let foo = ↓Bundle()


let foo = bar(bundle: ↓Bundle(), device: ↓UIDevice())


↓UIDevice.init()


↓Bundle.init()


let foo = ↓UIDevice.init()


let foo = ↓Bundle.init()


let foo = bar(bundle: ↓Bundle.init(), device: ↓UIDevice.init())

```

## Further Reading

* [SwiftLint - Discouraged Direct Initialization](https://github.com/realm/SwiftLint/blob/master/Rules.md#discouraged-direct-initialization)