Pattern: Discouraged call in `describe`/`context` block

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


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           beforeEach {
               let foo = Foo()
               foo.toto()
           }
           afterEach {
               let foo = Foo()
               foo.toto()
           }
           describe("bar") {
           }
           context("bar") {
           }
           it("bar") {
               let foo = Foo()
               foo.toto()
           }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
          itBehavesLike("bar")
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           it("does something") {
               let foo = Foo()
               foo.toto()
           }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       context("foo") {
           afterEach { toto.append(foo) }
       }
   }
}

```
Examples of **incorrect** code:
```swift

class TotoTests {
   override func spec() {
       describe("foo") {
           let foo = Foo()
       }
   }
}
class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           let foo = ↓Foo()
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           let foo = ↓Foo()
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           context("foo") {
               let foo = ↓Foo()
           }
           context("bar") {
               let foo = ↓Foo()
               ↓foo.bar()
               it("does something") {
                   let foo = Foo()
                   foo.toto()
               }
           }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           context("foo") {
               context("foo") {
                   beforeEach {
                       let foo = Foo()
                       foo.toto()
                   }
                   it("bar") {
                   }
                   context("foo") {
                       let foo = ↓Foo()
                   }
               }
           }
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       context("foo") {
           let foo = ↓Foo()
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       sharedExamples("foo") {
           let foo = ↓Foo()
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       describe("foo") {
           ↓foo()
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       context("foo") {
           ↓foo()
       }
   }
}


class TotoTests: QuickSpec {
   override func spec() {
       sharedExamples("foo") {
           ↓foo()
       }
   }
}

```

## Further Reading

* [SwiftLint - Quick Discouraged Call](https://github.com/realm/SwiftLint/blob/master/Rules.md#quick-discouraged-call)