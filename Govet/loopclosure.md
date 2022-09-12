Pattern: Reference to loop variable from within nested function

Issue: -

## Description

Checks for references to loop variables from within a function literal inside the loop body. It checks only instances where
the function literal is called in a defer or go statement that is the last statement in the loop body.

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

* [Go Vet - loopclosure](https://golang.org/cmd/vet/)
