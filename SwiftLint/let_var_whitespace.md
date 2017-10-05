Pattern: Malformed whitespace around `let`/`var`

Issue: -

## Description

`let` and `var` should be separated from other statements by a blank line.

Examples of **correct** code:
```swift
let a = 0
var x = 1

x = 2


a = 5

var x = 1


struct X {
	var a = 0
}


let a = 1 +
	2
let b = 5


var x: Int {
	return 0
}


var x: Int {
	let a = 0

	return a
}


#if os(macOS)
let a = 0
#endif


@available(swift 4)
let a = 0


class C {
	@objc
	var s: String = ""
}


class C {
	@objc
	func a() {}
}


class C {
	var x = 0
	lazy
	var y = 0
}


@available(OSX, introduced: 10.6)
@available(*, deprecated)
var x = 0


// swiftlint:disable superfluous_disable_command
// swiftlint:disable force_cast

let x = bar as! Bar

```
Examples of **incorrect** code:
```swift

var x = 1
↓x = 2


a = 5
↓var x = 1


struct X {
	let a
	↓func x() {}
}


var x = 0
↓@objc func f() {}


var x = 0
↓@objc
	func f() {}


@objc func f() {
}
↓var x = 0

```

## Further Reading

* [SwiftLint - Variable Declaration Whitespace](https://github.com/realm/SwiftLint/blob/master/Rules.md#variable-declaration-whitespace)