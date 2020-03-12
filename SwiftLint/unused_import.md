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

* [SwiftLint - Unused Import](https://realm.github.io/SwiftLint/unused_import.html)