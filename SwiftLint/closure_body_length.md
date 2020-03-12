Pattern: Closure body is too long

Issue: -

## Description

Closure bodies should not span too many lines.

Examples of **correct** code:
```swift
foo.bar { $0 }


foo.bar { toto in
}



foo.bar { toto in
	let a = 0
	// toto
	// toto
	// toto
	// toto
	// toto
	// toto
	// toto
	// toto
	// toto
	// toto
```
Examples of **incorrect** code:
```swift

foo.bar ↓{ toto in
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
	let a = 0
}
```

## Further Reading

* [SwiftLint - Closure Body Length](https://realm.github.io/SwiftLint/closure_body_length.html)