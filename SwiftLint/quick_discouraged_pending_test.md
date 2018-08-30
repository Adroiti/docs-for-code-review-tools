Pattern: Use of pending test

Issue: -

## Description

Used to discourage pending test. This test won't run while it's marked as pending.

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
       ↓xdescribe("foo") { }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       ↓xcontext("foo") { }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       ↓xit("foo") { }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           ↓xit("bar") { }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       context("foo") {
           ↓xit("bar") { }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           context("bar") {
               ↓xit("toto") { }
           }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       ↓pending("foo")
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       ↓xitBehavesLike("foo")
   }
}

```

## Further Reading

* [SwiftLint - Quick Discouraged Pending Test](https://github.com/realm/SwiftLint/blob/master/Rules.md#quick-discouraged-pending-test)