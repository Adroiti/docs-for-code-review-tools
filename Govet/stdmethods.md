Pattern: Malformed standard library method signature

Issue: -

## Description

Sometimes a type may be intended to satisfy an interface but may fail to
do so because of a mistake in its method signature.
For example, the result of this `WriteTo` method should be `(int64, error)`,
not error, to satisfy `io.WriterTo`:

```go
type myWriterTo struct{...}
	func (myWriterTo) WriteTo(w io.Writer) error { ... }
```	

This check ensures that each method whose name matches one of several
well-known interface methods from the standard library has the correct
signature for that interface.


## Further Reading

* [Go Vet - stdmethods](https://golang.org/cmd/vet/)
