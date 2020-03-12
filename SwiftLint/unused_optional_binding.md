Pattern: Use of `let _ =`

Issue: -

## Description

Prefer `!= nil` over `let _ =`.

Examples of **correct** code:
```swift
if let bar = Foo.optionalValue {
}


if let (_, second) = getOptionalTuple() {
}


if let (_, asd, _) = getOptionalTuple(), let bar = Foo.optionalValue {
}


if foo() { let _ = bar() }


if foo() { _ = bar() }


if case .some(_) = self {}


if let point = state.find({ _ in true }) {}

```
Examples of **incorrect** code:
```swift

if let ↓_ = Foo.optionalValue {
}


if let a = Foo.optionalValue, let ↓_ = Foo.optionalValue2 {
}


guard let a = Foo.optionalValue, let ↓_ = Foo.optionalValue2 {
}


if let (first, second) = getOptionalTuple(), let ↓_ = Foo.optionalValue {
}


if let (first, _) = getOptionalTuple(), let ↓_ = Foo.optionalValue {
}


if let (_, second) = getOptionalTuple(), let ↓_ = Foo.optionalValue {
}


if let ↓(_, _, _) = getOptionalTuple(), let bar = Foo.optionalValue {
}


func foo() {
if let ↓_ = bar {
}


if case .some(let ↓_) = self {}

```

## Further Reading

* [SwiftLint - Unused Optional Binding](https://realm.github.io/SwiftLint/unused_optional_binding.html)