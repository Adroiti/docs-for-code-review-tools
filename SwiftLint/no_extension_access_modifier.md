Pattern: Use of extension access modifier

Issue: -

## Description

Prefer not to use extension access modifiers.

Examples of **correct** code:
```swift
extension String {}


 extension String {}

```
Examples of **incorrect** code:
```swift

↓private extension String {}


↓public 
 extension String {}


↓open extension String {}


↓internal extension String {}


↓fileprivate extension String {}

```

## Further Reading

* [SwiftLint - No Extension Access Modifier](https://realm.github.io/SwiftLint/no_extension_access_modifier.html)