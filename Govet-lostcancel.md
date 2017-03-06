Pattern: Failure to call the cancelation function returned by `context.WithCancel`

Issue: -

## Description

The cancelation function returned by `context.WithCancel`, `WithTimeout`, and `WithDeadline` must be called or the new context will remain live until its parent context is cancelled.


Example of **incorrect** code:

```go
func _() {
	var ctx, cancel = context.WithCancel()
	// this return statement may be reached without using the cancel var
}
```

Example of **correct** code:

```go
func _() {
	ctx, cancel := context.WithCancel()
	defer cancel()
}
```

## Further Reading

* [Go Vet - Package context](https://golang.org/pkg/context/)
* [Go Vet - lostcancel](https://golang.org/cmd/vet/#hdr-Failure_to_call_the_cancelation_function_returned_by_WithCancel)
