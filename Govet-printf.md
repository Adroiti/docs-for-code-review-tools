Pattern: Suspicious calls to functions in the Printf family

Issue: -

## Description

Suspicious calls to functions in the Printf family, including any functions
with these names, disregarding case:

```
Print Printf Println
Fprint Fprintf Fprintln
Sprint Sprintf Sprintln
Error Errorf
Fatal Fatalf
Log Logf
Panic Panicf Panicln
```

## Further Reading

* [Go Vet - printf](https://golang.org/cmd/vet/#hdr-Suspicious_calls_to_functions_in_the_Printf_family)