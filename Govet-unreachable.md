Pattern: Unreachable code

Issue: -

## Description

Unreachable code can never be executed because there exists no control flow path to the code from the rest of the program. It is generally considered undesirable for a number of reasons, including increased code size and increased time and effort for maintainenance. Consider deleting unused code to resolve this issue.

Example of **incorrect** code:

```go
func _() int {
	print(1)
	return 2
	println() // "unreachable code"
}
```

Example of **correct** code:

```go
func _() int {
	print(1)
	return 2
}
```

## Further Reading

* [SourceMaking - Dead Code](https://sourcemaking.com/refactoring/smells/dead-code)
* [Go Vet - unreachable](https://golang.org/cmd/vet/#hdr-Unreachable_code)
