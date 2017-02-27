Pattern: Misuse of unsafe Pointers

Issue: -

## Description

This issue reports likely incorrect uses of `unsafe.Pointer` to convert integers to pointers. A conversion from `uintptr` to `unsafe.Pointer` is invalid if it implies that there is a `uintptr`-typed word in memory that holds a pointer value, because
that word will be invisible to stack copying and to the garbage collector.


Example of **incorrect** code:

```go
func test() {
	var y uintptr
	x = unsafe.Pointer(y) // possible misuse of unsafe.Pointer
}
```

It is safe if `x` is itself derived directly from an `unsafe.Pointer` via conversion and pointer arithmetic or if `x` is the result of `reflect.Value.Pointer` or `reflect.Value.UnsafeAddr` or obtained from the Data field of a `*reflect.SliceHeader` or `*reflect.StringHeader`.


Pointer allows a program to defeat the type system and read and write arbitrary memory. It should be used with extreme care.

## Further Reading

* [Go - Unsafe Pointer](https://golang.org/pkg/unsafe/#Pointer)
* [Go Vet - unsafeptr](https://golang.org/cmd/vet/#hdr-Misuse_of_unsafe_Pointers)
