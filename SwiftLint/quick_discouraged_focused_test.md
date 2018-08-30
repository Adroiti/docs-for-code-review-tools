Pattern: Use of focused test

Issue: -

## Description

Used to discourage focused test. Other tests won't run while this one is focused.

Examples of **correct** code:
```swift
class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           describe("bar") { } 
           context("bar") {
               it("bar") { }
           }
           it("bar") { }
           itBehavesLike("bar")
       }
   }
}

```
Examples of **incorrect** code:
```swift

class TotoTests: QuickSpec {
   override func spec() {
       ↓fdescribe("foo") { }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       ↓fcontext("foo") { }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       ↓fit("foo") { }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           ↓fit("bar") { }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       context("foo") {
           ↓fit("bar") { }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           context("bar") {
               ↓fit("toto") { }
           }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       ↓fitBehavesLike("foo")
   }
}

```

## Further Reading

* [SwiftLint - Quick Discouraged Focused Test](https://github.com/realm/SwiftLint/blob/master/Rules.md#quick-discouraged-focused-test)