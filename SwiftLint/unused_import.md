Pattern: Unused import

Issue: -

## Description

All imported modules should be required to make the file compile.

Examples of **correct** code:
```swift
import Dispatch
dispatchMain()


@testable import Dispatch
dispatchMain()


import Foundation
@objc
class A {}

```
Examples of **incorrect** code:
```swift

↓import Dispatch
struct A {
    static func dispatchMain() {}
}
A.dispatchMain()


↓import Foundation
dispatchMain()


↓import Foundation
// @objc
class A {}

```

## Further Reading

* [SwiftLint - Unused Import](https://github.com/realm/SwiftLint/blob/master/Rules.md#unused-import)