Pattern: Unused result of certain function calls

Issue: -

## Description

Calls to well-known functions and methods that return a value that is discarded. By default, this includes functions like `fmt.Errorf` and `fmt.Sprintf`.

## Further Reading

* [Go Vet - unusedresult](https://golang.org/cmd/vet/#hdr-Unused_result_of_certain_function_calls)
