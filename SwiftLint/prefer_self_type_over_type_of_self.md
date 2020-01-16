Pattern: Use of `type(of: self)`

Issue: -

## Description

Prefer `Self` over `type(of: self)` when accessing properties or calling methods.

Examples of **correct** code:

```swift
class Foo {
    func bar() {
        Self.baz()
    }
}

class Foo {
    func bar() {
        print(Self.baz)
    }
}

class A {
    func foo(param: B) {
        type(of: param).bar()
    }
}

class A {
    func foo() {
        print(type(of: self))
    }
}
```

Examples of **incorrect** code:

```swift
class Foo {
    func bar() {
        ↓type(of: self).baz()
    }
}

class Foo {
    func bar() {
        print(↓type(of: self).baz)
    }
}

class Foo {
    func bar() {
        print(↓Swift.type(of: self).baz)
    }
}
```

## Further Reading

* [SwiftLint - Prefer Self Type Over Type of Self](https://github.com/realm/SwiftLint/blob/master/Rules.md#prefer_self_type_over_type_of_self)