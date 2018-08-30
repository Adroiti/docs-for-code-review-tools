Pattern: Use of optional collection instead of empty collection

Issue: -

## Description

Prefer empty collection over optional collection.

Examples of **correct** code:
```swift
var foo: [Int]


var foo: [String: Int]


var foo: Set<String>


var foo: [String: [String: Int]]


let foo: [Int] = []


let foo: [String: Int] = [:]


let foo: Set<String> = []


let foo: [String: [String: Int]] = [:]


var foo: [Int] { return [] }


func foo() -> [Int] {}


func foo() -> [String: String] {}


func foo() -> Set<Int> {}


func foo() -> ([Int]) -> String {}


func foo(input: [String] = []) {}


func foo(input: [String: String] = [:]) {}


func foo(input: Set<String> = []) {}


class Foo {
	func foo() -> [Int] {}
}


class Foo {
	func foo() -> [String: String] {}
}


class Foo {
	func foo() -> Set<Int> {}
}


class Foo {
	func foo() -> ([Int]) -> String {}
}


struct Foo {
	func foo() -> [Int] {}
}


struct Foo {
	func foo() -> [String: String] {}
}


struct Foo {
	func foo() -> Set<Int> {}
}


struct Foo {
	func foo() -> ([Int]) -> String {}
}


enum Foo {
	func foo() -> [Int] {}
}


enum Foo {
	func foo() -> [String: String] {}
}


enum Foo {
	func foo() -> Set<Int> {}
}


enum Foo {
	func foo() -> ([Int]) -> String {}
}


class Foo {
	func foo(input: [String] = []) {}
}


class Foo {
	func foo(input: [String: String] = [:]) {}
}


class Foo {
	func foo(input: Set<String> = []) {}
}


struct Foo {
	func foo(input: [String] = []) {}
}


struct Foo {
	func foo(input: [String: String] = [:]) {}
}


struct Foo {
	func foo(input: Set<String> = []) {}
}


enum Foo {
	func foo(input: [String] = []) {}
}


enum Foo {
	func foo(input: [String: String] = [:]) {}
}


enum Foo {
	func foo(input: Set<String> = []) {}
}

```
Examples of **incorrect** code:
```swift

↓var foo: [Int]?


↓var foo: [String: Int]?


↓var foo: Set<String>?


↓let foo: [Int]? = nil


↓let foo: [String: Int]? = nil


↓let foo: Set<String>? = nil


↓var foo: [Int]? { return nil }


↓let foo: [Int]? { return nil }()


func ↓foo() -> [T]? {}


func ↓foo() -> [String: String]? {}


func ↓foo() -> [String: [String: String]]? {}


func ↓foo() -> [String: [String: String]?] {}


func ↓foo() -> Set<Int>? {}


static func ↓foo() -> [T]? {}


static func ↓foo() -> [String: String]? {}


static func ↓foo() -> [String: [String: String]]? {}


static func ↓foo() -> [String: [String: String]?] {}


static func ↓foo() -> Set<Int>? {}


func ↓foo() -> ([Int]?) -> String {}


func ↓foo() -> ([Int]) -> [String]? {}


func foo(↓input: [String: String]?) {}


func foo(↓input: [String: [String: String]]?) {}


func foo(↓input: [String: [String: String]?]) {}


func foo(↓↓input: [String: [String: String]?]?) {}


func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]


func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]


static func foo(↓input: [String: String]?) {}


static func foo(↓input: [String: [String: String]]?) {}


static func foo(↓input: [String: [String: String]?]) {}


static func foo(↓↓input: [String: [String: String]?]?) {}


static func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]


static func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]


class Foo {
	↓var foo: [Int]?
}


class Foo {
	↓var foo: [String: Int]?
}


class Foo {
	↓var foo: Set<String>?
}


class Foo {
	↓let foo: [Int]? = nil
}


class Foo {
	↓let foo: [String: Int]? = nil
}


class Foo {
	↓let foo: Set<String>? = nil
}


struct Foo {
	↓var foo: [Int]?
}


struct Foo {
	↓var foo: [String: Int]?
}


struct Foo {
	↓var foo: Set<String>?
}


struct Foo {
	↓let foo: [Int]? = nil
}


struct Foo {
	↓let foo: [String: Int]? = nil
}


struct Foo {
	↓let foo: Set<String>? = nil
}


class Foo {
	↓var foo: [Int]? { return nil }
}


class Foo {
	↓let foo: [Int]? { return nil }()
}


class Foo {
	↓var foo: Set<String>? { return nil }
}


class Foo {
	↓let foo: Set<String>? { return nil }()
}


struct Foo {
	↓var foo: [Int]? { return nil }
}


struct Foo {
	↓let foo: [Int]? { return nil }()
}


struct Foo {
	↓var foo: Set<String>? { return nil }
}


struct Foo {
	↓let foo: Set<String>? { return nil }()
}


enum Foo {
	↓var foo: [Int]? { return nil }
}


enum Foo {
	↓let foo: [Int]? { return nil }()
}


enum Foo {
	↓var foo: Set<String>? { return nil }
}


enum Foo {
	↓let foo: Set<String>? { return nil }()
}


class Foo {
	func ↓foo() -> [T]? {}
}


class Foo {
	func ↓foo() -> [String: String]? {}
}


class Foo {
	func ↓foo() -> [String: [String: String]]? {}
}


class Foo {
	func ↓foo() -> [String: [String: String]?] {}
}


class Foo {
	func ↓foo() -> Set<Int>? {}
}


class Foo {
	static func ↓foo() -> [T]? {}
}


class Foo {
	static func ↓foo() -> [String: String]? {}
}


class Foo {
	static func ↓foo() -> [String: [String: String]]? {}
}


class Foo {
	static func ↓foo() -> [String: [String: String]?] {}
}


class Foo {
	static func ↓foo() -> Set<Int>? {}
}


class Foo {
	func ↓foo() -> ([Int]?) -> String {}
}


class Foo {
	func ↓foo() -> ([Int]) -> [String]? {}
}


struct Foo {
	func ↓foo() -> [T]? {}
}


struct Foo {
	func ↓foo() -> [String: String]? {}
}


struct Foo {
	func ↓foo() -> [String: [String: String]]? {}
}


struct Foo {
	func ↓foo() -> [String: [String: String]?] {}
}


struct Foo {
	func ↓foo() -> Set<Int>? {}
}


struct Foo {
	static func ↓foo() -> [T]? {}
}


struct Foo {
	static func ↓foo() -> [String: String]? {}
}


struct Foo {
	static func ↓foo() -> [String: [String: String]]? {}
}


struct Foo {
	static func ↓foo() -> [String: [String: String]?] {}
}


struct Foo {
	static func ↓foo() -> Set<Int>? {}
}


struct Foo {
	func ↓foo() -> ([Int]?) -> String {}
}


struct Foo {
	func ↓foo() -> ([Int]) -> [String]? {}
}


enum Foo {
	func ↓foo() -> [T]? {}
}


enum Foo {
	func ↓foo() -> [String: String]? {}
}


enum Foo {
	func ↓foo() -> [String: [String: String]]? {}
}


enum Foo {
	func ↓foo() -> [String: [String: String]?] {}
}


enum Foo {
	func ↓foo() -> Set<Int>? {}
}


enum Foo {
	static func ↓foo() -> [T]? {}
}


enum Foo {
	static func ↓foo() -> [String: String]? {}
}


enum Foo {
	static func ↓foo() -> [String: [String: String]]? {}
}


enum Foo {
	static func ↓foo() -> [String: [String: String]?] {}
}


enum Foo {
	static func ↓foo() -> Set<Int>? {}
}


enum Foo {
	func ↓foo() -> ([Int]?) -> String {}
}


enum Foo {
	func ↓foo() -> ([Int]) -> [String]? {}
}


class Foo {
	func foo(↓input: [String: String]?) {}
}


class Foo {
	func foo(↓input: [String: [String: String]]?) {}
}


class Foo {
	func foo(↓input: [String: [String: String]?]) {}
}


class Foo {
	func foo(↓↓input: [String: [String: String]?]?) {}
}


class Foo {
	func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]
}


class Foo {
	func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]
}


class Foo {
	static func foo(↓input: [String: String]?) {}
}


class Foo {
	static func foo(↓input: [String: [String: String]]?) {}
}


class Foo {
	static func foo(↓input: [String: [String: String]?]) {}
}


class Foo {
	static func foo(↓↓input: [String: [String: String]?]?) {}
}


class Foo {
	static func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]
}


class Foo {
	static func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]
}


struct Foo {
	func foo(↓input: [String: String]?) {}
}


struct Foo {
	func foo(↓input: [String: [String: String]]?) {}
}


struct Foo {
	func foo(↓input: [String: [String: String]?]) {}
}


struct Foo {
	func foo(↓↓input: [String: [String: String]?]?) {}
}


struct Foo {
	func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]
}


struct Foo {
	func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]
}


struct Foo {
	static func foo(↓input: [String: String]?) {}
}


struct Foo {
	static func foo(↓input: [String: [String: String]]?) {}
}


struct Foo {
	static func foo(↓input: [String: [String: String]?]) {}
}


struct Foo {
	static func foo(↓↓input: [String: [String: String]?]?) {}
}


struct Foo {
	static func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]
}


struct Foo {
	static func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]
}


enum Foo {
	func foo(↓input: [String: String]?) {}
}


enum Foo {
	func foo(↓input: [String: [String: String]]?) {}
}


enum Foo {
	func foo(↓input: [String: [String: String]?]) {}
}


enum Foo {
	func foo(↓↓input: [String: [String: String]?]?) {}
}


enum Foo {
	func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]
}


enum Foo {
	func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]
}


enum Foo {
	static func foo(↓input: [String: String]?) {}
}


enum Foo {
	static func foo(↓input: [String: [String: String]]?) {}
}


enum Foo {
	static func foo(↓input: [String: [String: String]?]) {}
}


enum Foo {
	static func foo(↓↓input: [String: [String: String]?]?) {}
}


enum Foo {
	static func foo<K, V>(_ dict1: [K: V], ↓_ dict2: [K: V]?) -> [K: V]
}


enum Foo {
	static func foo<K, V>(dict1: [K: V], ↓dict2: [K: V]?) -> [K: V]
}

```

## Further Reading

* [SwiftLint - Discouraged Optional Collection](https://github.com/realm/SwiftLint/blob/master/Rules.md#discouraged-optional-collection)