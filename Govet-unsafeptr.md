Pattern: Misuse of unsafe Pointers

Issue: -

## Description

Likely incorrect uses of unsafe.Pointer to convert integers to pointers. A
conversion from uintptr to unsafe.Pointer is invalid if it implies that
there is a uintptr-typed word in memory that holds a pointer value, because
that word will be invisible to stack copying and to the garbage collector.

## Further Reading

* [Go Vet - unsafeptr](https://golang.org/cmd/vet/#hdr-Misuse_of_unsafe_Pointers)