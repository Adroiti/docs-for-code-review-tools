Pattern: Unused result of methods of type func() 

Issue: -

## Description

This rule enforces to use return value of call to `Error` and `String` methods.

Example of **incorrect** code:

```go
func _() {
	var buf bytes.Buffer
	buf.String() // result of bytes.Buffer.String call not used
}
```

Example of **correct** code:

```go
func _() {
	var buf bytes.Buffer
	result = buf.String()
}
```

## Further Reading

* [Go Vet - unusedresult](https://golang.org/cmd/vet/#hdr-Unused_result_of_certain_function_calls)
