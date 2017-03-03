Pattern: `Nil` function comparison

Issue: -

## Description

Comparisons between functions and `nil` result in _redundant_ (always `true`) or _unreachable_ (always `false`) code.


_Redundant_ code may increase maintenance costs by making code more difficult to change and to understand. Remove such code to resolve this issue.


_Unreachable_ code is generally considered undesirable for a number of reasons, including increased code size and increased time and effort for maintainenance. Update or remove such code to resolve this issue.


Example of **incorrect** code:

```go
func F() {}

func Comparison() {
  	if F == nil { // comparison of function F == nil is always false
		panic("can't happen")
	}
}
```

Example of **correct** code:

```go
func F() {}

var Fv = F

func Comparison() {
	if Fv == nil {
		// no error; func vars or fields may be nil
	}
}
```

## Further Reading

* [Go - Comparison operators](https://golang.org/ref/spec#Comparison_operators)
* [Go Vet - nilfunc](https://golang.org/cmd/vet/#hdr-Nil_function_comparison)
