Pattern: Use of `someBool = !someBool` instead of `someBool.toggle()`

Issue: -

## Description

Prefer `someBool.toggle()` over `someBool = !someBool`.

Examples of **correct** code:
```swift
isHidden.toggle()


view.clipsToBounds.toggle()


func foo() { abc.toggle() }


view.clipsToBounds = !clipsToBounds


disconnected = !connected

```
Examples of **incorrect** code:
```swift

↓isHidden = !isHidden


↓view.clipsToBounds = !view.clipsToBounds


func foo() { ↓abc = !abc }

```

## Further Reading

* [SwiftLint - Toggle Bool](https://github.com/realm/SwiftLint/blob/master/Rules.md#toggle-bool)