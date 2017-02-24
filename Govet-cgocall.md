Pattern: Invalid uses of cgo

Issue: -

## Description

This rules checks for types that may not be passed to `cgo` calls.

Example of **incorrect** code:

```go
import "C"

import "unsafe"

func CgoTests() {
	var c chan bool
	C.f(*(*unsafe.Pointer)(unsafe.Pointer(&c))) // embedded pointer
	C.f(unsafe.Pointer(&c))                     // embedded pointer
}
```

Example of **correct** code:

```go
import "C"

import "unsafe"

func CgoTests() {
	var i int
	C.f(*(*unsafe.Pointer)(unsafe.Pointer(&i)))
	C.f(unsafe.Pointer(&i))
}
```

## Further Reading

* [Go - Command cgo](https://golang.org/cmd/cgo/)
* [golang - cgo - Common Pitfalls](https://github.com/golang/go/wiki/cgo#common-pitfalls)
* [Go Vet - cgocall](https://golang.org/cmd/vet/#hdr-Invalid_uses_of_cgo)
