Pattern: HTTP responses used incorrectly

Issue: -

## Description

Mistakes deferring a function call on an HTTP response before checking whether the error returned with the response was nil.

## Further Reading

* [Go Vet - httpresponse](https://golang.org/cmd/vet/#hdr-HTTP_responses_used_incorrectly)