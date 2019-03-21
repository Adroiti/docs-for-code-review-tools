Pattern: Missing `deinit` method

Issue: -

## Description

Ensures that all classes have a `deinit` method. The purpose of this is to make memory leak debugging easier so all classes have a place to set a breakpoint to track deallocation.

Examples of **correct** code:

```swift
class Apple {
    deinit { }
}


enum Banana { }


protocol Cherry { }


struct Damson { }


class Outer {
    deinit { print("Deinit Outer") }
    class Inner {
        deinit { print("Deinit Inner") }
    }
}

```
Examples of **incorrect** code:
```swift

↓class Apple { }


↓class Banana: NSObject, Equatable { }


↓class Cherry {
    // deinit { }
}


↓class Damson {
    func deinitialize() { }
}


class Outer {
    func hello() -> String { return "outer" }
    deinit { }
    ↓class Inner {
        func hello() -> String { return "inner" }
    }
}


↓class Outer {
    func hello() -> String { return "outer" }
    class Inner {
        func hello() -> String { return "inner" }
        deinit { }
    }
}

```

## Further Reading

* [SwiftLint - Required Deinit](https://github.com/realm/SwiftLint/blob/master/Rules.md#required-deinit)