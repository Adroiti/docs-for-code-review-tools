Pattern: Use of optional boolean

Issue: -

## Description

Prefer non-optional booleans over optional booleans.

Examples of **correct** code:
```swift
var foo: Bool


var foo: [String: Bool]


var foo: [Bool]


let foo: Bool = true


let foo: Bool = false


let foo: [String: Bool] = [:]


let foo: [Bool] = []


var foo: Bool { return true }


let foo: Bool { return false }()


func foo() -> Bool {}


func foo() -> [String: Bool] {}


func foo() -> ([Bool]) -> String {}


func foo(input: Bool = true) {}


func foo(input: [String: Bool] = [:]) {}


func foo(input: [Bool] = []) {}


class Foo {
	func foo() -> Bool {}
}


class Foo {
	func foo() -> [String: Bool] {}
}


class Foo {
	func foo() -> ([Bool]) -> String {}
}


struct Foo {
	func foo() -> Bool {}
}


struct Foo {
	func foo() -> [String: Bool] {}
}


struct Foo {
	func foo() -> ([Bool]) -> String {}
}


enum Foo {
	func foo() -> Bool {}
}


enum Foo {
	func foo() -> [String: Bool] {}
}


enum Foo {
	func foo() -> ([Bool]) -> String {}
}


class Foo {
	func foo(input: Bool = true) {}
}


class Foo {
	func foo(input: [String: Bool] = [:]) {}
}


class Foo {
	func foo(input: [Bool] = []) {}
}


struct Foo {
	func foo(input: Bool = true) {}
}


struct Foo {
	func foo(input: [String: Bool] = [:]) {}
}


struct Foo {
	func foo(input: [Bool] = []) {}
}


enum Foo {
	func foo(input: Bool = true) {}
}


enum Foo {
	func foo(input: [String: Bool] = [:]) {}
}


enum Foo {
	func foo(input: [Bool] = []) {}
}

```
Examples of **incorrect** code:
```swift

var foo: ↓Bool?


var foo: [String: ↓Bool?]


var foo: [↓Bool?]


let foo: ↓Bool? = nil


let foo: [String: ↓Bool?] = [:]


let foo: [↓Bool?] = []


let foo = ↓Optional.some(false)


let foo = ↓Optional.some(true)


var foo: ↓Bool? { return nil }


let foo: ↓Bool? { return nil }()


func foo() -> ↓Bool? {}


func foo() -> [String: ↓Bool?] {}


func foo() -> [↓Bool?] {}


static func foo() -> ↓Bool? {}


static func foo() -> [String: ↓Bool?] {}


static func foo() -> [↓Bool?] {}


func foo() -> (↓Bool?) -> String {}


func foo() -> ([Int]) -> ↓Bool? {}


func foo(input: ↓Bool?) {}


func foo(input: [String: ↓Bool?]) {}


func foo(input: [↓Bool?]) {}


static func foo(input: ↓Bool?) {}


static func foo(input: [String: ↓Bool?]) {}


static func foo(input: [↓Bool?]) {}


class Foo {
	var foo: ↓Bool?
}


class Foo {
	var foo: [String: ↓Bool?]
}


class Foo {
	let foo: ↓Bool? = nil
}


class Foo {
	let foo: [String: ↓Bool?] = [:]
}


class Foo {
	let foo: [↓Bool?] = []
}


struct Foo {
	var foo: ↓Bool?
}


struct Foo {
	var foo: [String: ↓Bool?]
}


struct Foo {
	let foo: ↓Bool? = nil
}


struct Foo {
	let foo: [String: ↓Bool?] = [:]
}


struct Foo {
	let foo: [↓Bool?] = []
}


class Foo {
	var foo: ↓Bool? { return nil }
}


class Foo {
	let foo: ↓Bool? { return nil }()
}


struct Foo {
	var foo: ↓Bool? { return nil }
}


struct Foo {
	let foo: ↓Bool? { return nil }()
}


enum Foo {
	var foo: ↓Bool? { return nil }
}


enum Foo {
	let foo: ↓Bool? { return nil }()
}


class Foo {
	func foo() -> ↓Bool? {}
}


class Foo {
	func foo() -> [String: ↓Bool?] {}
}


class Foo {
	func foo() -> [↓Bool?] {}
}


class Foo {
	static func foo() -> ↓Bool? {}
}


class Foo {
	static func foo() -> [String: ↓Bool?] {}
}


class Foo {
	static func foo() -> [↓Bool?] {}
}


class Foo {
	func foo() -> (↓Bool?) -> String {}
}


class Foo {
	func foo() -> ([Int]) -> ↓Bool? {}
}


struct Foo {
	func foo() -> ↓Bool? {}
}


struct Foo {
	func foo() -> [String: ↓Bool?] {}
}


struct Foo {
	func foo() -> [↓Bool?] {}
}


struct Foo {
	static func foo() -> ↓Bool? {}
}


struct Foo {
	static func foo() -> [String: ↓Bool?] {}
}


struct Foo {
	static func foo() -> [↓Bool?] {}
}


struct Foo {
	func foo() -> (↓Bool?) -> String {}
}


struct Foo {
	func foo() -> ([Int]) -> ↓Bool? {}
}


enum Foo {
	func foo() -> ↓Bool? {}
}


enum Foo {
	func foo() -> [String: ↓Bool?] {}
}


enum Foo {
	func foo() -> [↓Bool?] {}
}


enum Foo {
	static func foo() -> ↓Bool? {}
}


enum Foo {
	static func foo() -> [String: ↓Bool?] {}
}


enum Foo {
	static func foo() -> [↓Bool?] {}
}


enum Foo {
	func foo() -> (↓Bool?) -> String {}
}


enum Foo {
	func foo() -> ([Int]) -> ↓Bool? {}
}


class Foo {
	func foo(input: ↓Bool?) {}
}


class Foo {
	func foo(input: [String: ↓Bool?]) {}
}


class Foo {
	func foo(input: [↓Bool?]) {}
}


class Foo {
	static func foo(input: ↓Bool?) {}
}


class Foo {
	static func foo(input: [String: ↓Bool?]) {}
}


class Foo {
	static func foo(input: [↓Bool?]) {}
}


struct Foo {
	func foo(input: ↓Bool?) {}
}


struct Foo {
	func foo(input: [String: ↓Bool?]) {}
}


struct Foo {
	func foo(input: [↓Bool?]) {}
}


struct Foo {
	static func foo(input: ↓Bool?) {}
}


struct Foo {
	static func foo(input: [String: ↓Bool?]) {}
}


struct Foo {
	static func foo(input: [↓Bool?]) {}
}


enum Foo {
	func foo(input: ↓Bool?) {}
}


enum Foo {
	func foo(input: [String: ↓Bool?]) {}
}


enum Foo {
	func foo(input: [↓Bool?]) {}
}


enum Foo {
	static func foo(input: ↓Bool?) {}
}


enum Foo {
	static func foo(input: [String: ↓Bool?]) {}
}


enum Foo {
	static func foo(input: [↓Bool?]) {}
}

```

## Further Reading

* [SwiftLint - Discouraged Optional Boolean](https://github.com/realm/SwiftLint/blob/master/Rules.md#discouraged-optional-boolean)