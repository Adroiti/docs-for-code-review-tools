Pattern: Useless shift

Issue: -

## Description

This rule checks if shift or shift-assign operations shift by more than the length of the underlying variable. Update variable type or shift count to make your intention and code more clear.


Example of **incorrect** code:

```go
func ShiftTest() {
  var i8 int8
  _ = i8 >> 8    // i8 is too small for shift of 8
}
```

Example of **correct** code:

```go
func ShiftTest() {
  var i8 int8
  _ = i8 << 7
}
```

## Further Reading

* [Go - Arithmetic operators](https://golang.org/ref/spec#Arithmetic_operators)
* [Go Vet - shift](https://golang.org/cmd/vet/#hdr-Shifts)
