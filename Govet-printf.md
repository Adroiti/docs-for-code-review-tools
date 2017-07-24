Pattern: Suspicious call to function in the `Printf` family

Issue: -

## Description

Invalid calls in the `Printf` family or calls that do not match formats against args may lead to confusion as code will not work as expected. This rule checks for any functions with these names, disregarding case:

```
Print Printf Println
Fprint Fprintf Fprintln
Sprint Sprintf Sprintln
Error Errorf
Fatal Fatalf
Log Logf
Panic Panicf Panicln
```

Example of **incorrect** code:

```go
fmt.Printf("expected to find %s") // missing argument, format reads arg 1, have 0 args 
```

Example of **correct** code:

```go
fmt.Printf("expected to find %s", "arg value")
```

## Further Reading

* [Effective Go - Printing](https://golang.org/doc/effective_go.html#printing)
* [Go Vet - printf](https://golang.org/cmd/vet/#hdr-Printf_family)
