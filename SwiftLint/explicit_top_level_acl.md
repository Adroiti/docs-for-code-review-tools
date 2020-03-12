Pattern: Missing explicit top level _ACL_

Issue: -

## Description

Top-level declarations should specify _Access Control Level_ keywords explicitly.

Examples of **correct** code:
```swift
internal enum A {}


public final class B {}


private struct C {}


internal enum A {
 enum B {}
}


internal final class Foo {}


internal
class Foo {}


internal func a() {}

```
Examples of **incorrect** code:
```swift

enum A {}


final class B {}


struct C {}


func a() {}


internal let a = 0
func b() {}

```

## Further Reading

* [SwiftLint - Explicit Top Level ACL](https://realm.github.io/SwiftLint/explicit_top_level_acl.html)