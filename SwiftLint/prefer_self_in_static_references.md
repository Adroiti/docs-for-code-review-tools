Pattern: Missing use of `Self` for static reference

Issue: -

## Description

Static references should be prefixed by `Self` instead of the class name.

Examples of **correct** code:

```swift
class C {
	static private(set) var i = 0, j = C.i
	let h = C.i
	@GreaterThan(C.j) var k: Int
}

class `Self` {
	static let i = 0
	func f() -> Int { Self.i }
}
```

Examples of **incorrect** code:

```swift
struct C {
	static let i = 0
	static let j = ↓C.i
}

struct S {
	static let i = 0
	func f() -> Int { ↓S.i }
}
```

## Further Reading

* [SwiftLint - Prefer Self in Static References](https://realm.github.io/SwiftLint/prefer_self_in_static_references.html)