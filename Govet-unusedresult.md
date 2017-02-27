Pattern: Unused result of certain function calls

Issue: -

## Description

This rule enforces to use return value of well-known pure functions - `errors.New`, `fmt.Errorf` , `fmt.Sprintf`, `fmt.Sprint`, `sort.Reverse` - as well as `Error` and `String` methods.

Example of **incorrect** code:

```go
func _() {
	fmt.Errorf("") // result of fmt.Errorf call not used
}
```

Example of **correct** code:

```go
func _() {
	_ = fmt.Errorf("")
}
```

## Further Reading

* [Go Vet - unusedresult](https://golang.org/cmd/vet/#hdr-Unused_result_of_certain_function_calls)
