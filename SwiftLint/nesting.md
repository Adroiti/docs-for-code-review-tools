Pattern: Too many nested blocks

Issue: -

## Description

Types should be nested at most 1 level deep, and statements should be nested at most 5 levels deep.

Examples of **correct** code:
```swift
class Class0 { class Class1 {} }


func func0() {
func func1() {
func func2() {
func func3() {
func func4() { func func5() {
}
}
}
}
}
}


struct Class0 { struct Class1 {} }


func func0() {
func func1() {
func func2() {
func func3() {
func func4() { func func5() {
}
}
}
}
}
}


enum Class0 { enum Class1 {} }


func func0() {
func func1() {
func func2() {
func func3() {
func func4() { func func5() {
}
}
}
}
}
}


enum Enum0 { enum Enum1 { case Case } }

```
Examples of **incorrect** code:
```swift

class A { class B { ↓class C {} } }


struct A { struct B { ↓struct C {} } }


enum A { enum B { ↓enum C {} } }


func func0() {
func func1() {
func func2() {
func func3() {
func func4() { func func5() {
↓func func6() {
}
}
}
}
}
}
}

```

## Further Reading

* [SwiftLint - Nesting](https://realm.github.io/SwiftLint/nesting.html)