Pattern: Common mistaken usages of the sync/atomic package

Issue: -

## Description

This rule walks `atomic.Add*` method calls checking for assigning the return value to the same variable being used in the operation.


Example of **incorrect** code:

```go
func AtomicTest() {
	x := uint64(1)
	x = atomic.AddUint64(&x, 1) // direct assignment to atomic value
}
```

Example of **correct** code:

```go
func AtomicTest() {
	x := uint64(1)
	y = atomic.AddUint64(&x, 1)
}
```

In general, these functions require great care to be used correctly. Except for special, low-level applications, synchronization is better done with channels or the facilities of the sync package. Share memory by communicating; don't communicate by sharing memory.

## Further Reading

* [Go - Package atomic](https://golang.org/pkg/sync/atomic/)
* [Go Vet - atomic](https://golang.org/cmd/vet/#hdr-Atomic_mistakes)
