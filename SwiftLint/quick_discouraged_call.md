Pattern: Call inside `describe`/`context` block

Issue: -

## Description

Avoid discouraged calls inside `describe` and `context` blocks.

Examples of **correct** code:
```swift
class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           beforeEach {
               let foo = Foo()
               foo.toto()
           }
       }
   }
}

```
Examples of **incorrect** code:
```swift
class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           let foo = ↓Foo()
       }
   }
}
```

## Further Reading

* [SwiftLint - Quick Discouraged Call](https://realm.github.io/SwiftLint/quick_discouraged_call.html)