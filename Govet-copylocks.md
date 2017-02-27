Pattern: Locks are passed by value

Issue: -

## Description

Lock can be passed by value or by pointer. Passing lock by value creates a copy of the lock and may cause unexpected behavior. This issue can be safely ignored if it's your intention.


Example of **incorrect** code:

```go
func BadFunc(sync.Mutex) {} // BadFunc passes lock by value: sync.Mutex
```

Example of **correct** code:

```go
func OkFunc(*sync.Mutex) {}
```

## Further Reading

* [golangspec - Detect locks passed by value in Go](https://medium.com/golangspec/detect-locks-passed-by-value-in-go-efb4ac9a3f2b)
* [Go Vet - copylocks](https://golang.org/cmd/vet/#hdr-Copying_locks)
