Pattern: Use of explicit `.init()`

Issue: -

## Description

Explicitly calling `.init()` should be avoided.

Examples of **correct** code:
```swift
import Foundation; class C: NSObject { override init() { super.init() }}


struct S { let n: Int }; extension S { init() { self.init(n: 1) } }


[1].flatMap(String.init)


[String.self].map { $0.init(1) }


[String.self].map { type in type.init(1) }

```
Examples of **incorrect** code:
```swift

[1].flatMap{String↓.init($0)}


[String.self].map { Type in Type↓.init(1) }

```

## Further Reading

* [SwiftLint - Explicit Init](https://realm.github.io/SwiftLint/explicit_init.html)