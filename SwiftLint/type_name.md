Pattern: Invalid type name

Issue: -

## Description

Type name should only contain alphanumeric characters, start with an uppercase character and span between 3 and 40 characters in length.

Examples of **correct** code:
```swift
class MyType {}


private class _MyType {}


class AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA {}


struct MyType {}


private struct _MyType {}


struct AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA {}


enum MyType {}


private enum _MyType {}


enum AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA {}


typealias Foo = Void


private typealias Foo = Void


protocol Foo {
 associatedtype Bar
 }


protocol Foo {
 associatedtype Bar: Equatable
 }


enum MyType {
case value
}

```
Examples of **incorrect** code:
```swift

↓class myType {}


↓class _MyType {}


private ↓class MyType_ {}


↓class My {}


↓class AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA {}


↓struct myType {}


↓struct _MyType {}


private ↓struct MyType_ {}


↓struct My {}


↓struct AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA {}


↓enum myType {}


↓enum _MyType {}


private ↓enum MyType_ {}


↓enum My {}


↓enum AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA {}


typealias ↓X = Void


private typealias ↓Foo_Bar = Void


private typealias ↓foo = Void


typealias ↓AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA = Void


protocol Foo {
 associatedtype ↓X
 }


protocol Foo {
 associatedtype ↓Foo_Bar: Equatable
 }


protocol Foo {
 associatedtype ↓AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
 }

```

## Further Reading

* [SwiftLint - Type Name](https://realm.github.io/SwiftLint/type_name.html)