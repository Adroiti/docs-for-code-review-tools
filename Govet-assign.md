Pattern: Useless assignments

Issue: -

## Description

This rule checks for for assignments of the form `<expr> = <expr>`. These are almost always unnecessary, and even when they aren't they are usually a mistake. Consider removing such code to increase readability.


Example of **incorrect** code:

```go
func (s *ST) SetX(x int) {
	x = x // self-assignment of x to x
}
```

Example of **correct** code:

```go
func (s *ST) SetX(x int) {
	s.x = x
}
```

## Further Reading

* [Go Vet - assign](https://golang.org/cmd/vet/#hdr-Useless_assignments)
