Pattern: Common mistaken usages of tests/documentation

Issue: -

## Description

To fully use automated testing of Go packages you should apply naming and signature conventions for `Test`, `Benchmark` and `Example` functions. This rules checks for malformed names, wrong signatures and examples documenting inexistent identifiers.

Example of **incorrect** code:

```go
func ExampleSalutations() {
        fmt.Println("hello, and")
        fmt.Println("goodbye")
}
```

Example of **correct** code:

```go
func Examplesalutations() {
        fmt.Println("hello, and")
        fmt.Println("goodbye")
}
```
## Further Reading

* [Go - Package testing](https://golang.org/pkg/testing/)
* [Go - How to Write Go Code](https://golang.org/doc/code.html#Testing)
* [Go Vet - tests](https://golang.org/cmd/vet/#hdr-Tests_and_documentation_examples)
