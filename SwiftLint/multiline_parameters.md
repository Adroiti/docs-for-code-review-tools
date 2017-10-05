Pattern: Use of multi-line parameters

Issue: -

## Description

Functions and methods parameters should be either on the same line, or one per line.

Examples of **correct** code:
```swift
func foo() { }


func foo(param1: Int) { }


func foo(param1: Int, param2: Bool) { }


func foo(param1: Int, param2: Bool, param3: [String]) { }


func foo(param1: Int,
         param2: Bool,
         param3: [String]) { }


func foo(_ param1: Int, param2: Int, param3: Int) -> (Int) -> Int {
   return { x in x + param1 + param2 + param3 }
}


static func foo() { }


static func foo(param1: Int) { }


static func foo(param1: Int, param2: Bool) { }


static func foo(param1: Int, param2: Bool, param3: [String]) { }


static func foo(param1: Int,
                param2: Bool,
                param3: [String]) { }


protocol Foo {
	func foo() { }
}


protocol Foo {
	func foo(param1: Int) { }
}


protocol Foo {
	func foo(param1: Int, param2: Bool) { }
}


protocol Foo {
	func foo(param1: Int, param2: Bool, param3: [String]) { }
}


protocol Foo {
   func foo(param1: Int,
            param2: Bool,
            param3: [String]) { }
}


protocol Foo {
	static func foo(param1: Int, param2: Bool, param3: [String]) { }
}


protocol Foo {
   static func foo(param1: Int,
                   param2: Bool,
                   param3: [String]) { }
}


protocol Foo {
	class func foo(param1: Int, param2: Bool, param3: [String]) { }
}


protocol Foo {
   class func foo(param1: Int,
                  param2: Bool,
                  param3: [String]) { }
}


enum Foo {
	func foo() { }
}


enum Foo {
	func foo(param1: Int) { }
}


enum Foo {
	func foo(param1: Int, param2: Bool) { }
}


enum Foo {
	func foo(param1: Int, param2: Bool, param3: [String]) { }
}


enum Foo {
   func foo(param1: Int,
            param2: Bool,
            param3: [String]) { }
}


enum Foo {
	static func foo(param1: Int, param2: Bool, param3: [String]) { }
}


enum Foo {
   static func foo(param1: Int,
                   param2: Bool,
                   param3: [String]) { }
}


struct Foo {
	func foo() { }
}


struct Foo {
	func foo(param1: Int) { }
}


struct Foo {
	func foo(param1: Int, param2: Bool) { }
}


struct Foo {
	func foo(param1: Int, param2: Bool, param3: [String]) { }
}


struct Foo {
   func foo(param1: Int,
            param2: Bool,
            param3: [String]) { }
}


struct Foo {
	static func foo(param1: Int, param2: Bool, param3: [String]) { }
}


struct Foo {
   static func foo(param1: Int,
                   param2: Bool,
                   param3: [String]) { }
}


class Foo {
	func foo() { }
}


class Foo {
	func foo(param1: Int) { }
}


class Foo {
	func foo(param1: Int, param2: Bool) { }
}


class Foo {
	func foo(param1: Int, param2: Bool, param3: [String]) { }
	}


class Foo {
   func foo(param1: Int,
            param2: Bool,
            param3: [String]) { }
}


class Foo {
	class func foo(param1: Int, param2: Bool, param3: [String]) { }
}


class Foo {
   class func foo(param1: Int,
                  param2: Bool,
                  param3: [String]) { }
}

```
Examples of **incorrect** code:
```swift

func ↓foo(_ param1: Int,
          param2: Int, param3: Int) -> (Int) -> Int {
   return { x in x + param1 + param2 + param3 }
}


protocol Foo {
   func ↓foo(param1: Int,
             param2: Bool, param3: [String]) { }
}


protocol Foo {
   func ↓foo(param1: Int, param2: Bool,
             param3: [String]) { }
}


protocol Foo {
   static func ↓foo(param1: Int,
                    param2: Bool, param3: [String]) { }
}


protocol Foo {
   static func ↓foo(param1: Int, param2: Bool,
                    param3: [String]) { }
}


protocol Foo {
   class func ↓foo(param1: Int,
                   param2: Bool, param3: [String]) { }
}


protocol Foo {
   class func ↓foo(param1: Int, param2: Bool,
                   param3: [String]) { }
}


enum Foo {
   func ↓foo(param1: Int,
             param2: Bool, param3: [String]) { }
}


enum Foo {
   func ↓foo(param1: Int, param2: Bool,
             param3: [String]) { }
}


enum Foo {
   static func ↓foo(param1: Int,
                    param2: Bool, param3: [String]) { }
}


enum Foo {
   static func ↓foo(param1: Int, param2: Bool,
                    param3: [String]) { }
}


struct Foo {
   func ↓foo(param1: Int,
             param2: Bool, param3: [String]) { }
}


struct Foo {
   func ↓foo(param1: Int, param2: Bool,
             param3: [String]) { }
}


struct Foo {
   static func ↓foo(param1: Int,
                    param2: Bool, param3: [String]) { }
}


struct Foo {
   static func ↓foo(param1: Int, param2: Bool,
                    param3: [String]) { }
}


class Foo {
   func ↓foo(param1: Int,
             param2: Bool, param3: [String]) { }
}


class Foo {
   func ↓foo(param1: Int, param2: Bool,
             param3: [String]) { }
}


class Foo {
   class func ↓foo(param1: Int,
                   param2: Bool, param3: [String]) { }
}


class Foo {
   class func ↓foo(param1: Int, param2: Bool,
                   param3: [String]) { }
}

```

## Further Reading

* [SwiftLint - Multiline Parameters](https://github.com/realm/SwiftLint/blob/master/Rules.md#multiline-parameters)