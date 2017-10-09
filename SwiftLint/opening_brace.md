Pattern: Malformed `{`

Issue: -

## Description

Opening braces should be preceded by a single space and on the same line as the declaration.

Examples of **correct** code:
```swift
func abc() {
}


[].map() { $0 }


[].map({ })


if let a = b { }


while a == b { }


guard let a = b else { }


if
	let a = b,
	let c = d
	where a == c
{ }


while
	let a = b,
	let c = d
	where a == c
{ }


guard
	let a = b,
	let c = d
	where a == c else
{ }


struct Rule {}


struct Parent {
	struct Child {
		let foo: Int
	}
}

```
Examples of **incorrect** code:
```swift

func abc()↓{
}


func abc()
	↓{ }


[].map()↓{ $0 }


[].map( ↓{ } )


if let a = b↓{ }


while a == b↓{ }


guard let a = b else↓{ }


if
	let a = b,
	let c = d
	where a == c↓{ }


while
	let a = b,
	let c = d
	where a == c↓{ }


guard
	let a = b,
	let c = d
	where a == c else↓{ }


struct Rule↓{}


struct Rule
↓{
}


struct Rule

	↓{
}


struct Parent {
	struct Child
	↓{
		let foo: Int
	}
}

```

## Further Reading

* [SwiftLint - Opening Brace Spacing](https://github.com/realm/SwiftLint/blob/master/Rules.md#opening-brace-spacing)