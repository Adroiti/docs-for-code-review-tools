Pattern: Failure to call the cancelation function returned by context.WithCancel.

Issue: -

## Description

The cancelation function returned by context.WithCancel, WithTimeout, and
WithDeadline must be called or the new context will remain live until its
parent context is cancelled. (The background context is never cancelled.)

## Further Reading

* [Go Vet - lostcancel](https://golang.org/cmd/vet/#hdr-Failure_to_call_the_cancelation_function_returned_by_context.WithCancel.)