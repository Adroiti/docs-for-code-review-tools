Pattern: Malformed deployment target

Issue: -

## Description

Validate that `@availability` attributes and `#available` conditions are not using a version that is satisfied by the deployment target.

Examples of **correct** code:
```swift
@available(iOS 12.0, *)
class A {}


@available(watchOS 4.0, *)
class A {}


@available(swift 3.0.2)
class A {}


class A {}


if #available(iOS 10.0, *) {}


if #available(iOS 10, *) {}


guard #available(iOS 12.0, *) else { return }

```
Examples of **incorrect** code:
```swift

↓@available(iOS 6.0, *)
class A {}


↓@available(iOS 7.0, *)
class A {}


↓@available(iOS 6, *)
class A {}


↓@available(iOS 6.0, macOS 10.12, *)
 class A {}


↓@available(macOS 10.12, iOS 6.0, *)
 class A {}


↓@available(macOS 10.7, *)
class A {}


↓@available(OSX 10.7, *)
class A {}


↓@available(watchOS 0.9, *)
class A {}


↓@available(tvOS 8, *)
class A {}


if ↓#available(iOS 6.0, *) {}


if ↓#available(iOS 6, *) {}


guard ↓#available(iOS 6.0, *) else { return }

```

## Further Reading

* [SwiftLint - Deployment Target](https://github.com/realm/SwiftLint/blob/master/Rules.md#deployment-target)