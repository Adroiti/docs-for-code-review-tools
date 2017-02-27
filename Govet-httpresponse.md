Pattern: HTTP responses used incorrectly

Issue: -

## Description

This rule ensures that errors are checked before using HTTP Response.


Example of **incorrect** code:

```go
func badHTTPGet() {
	res, err := http.Get("http://foo.com")
	defer res.Body.Close() // using res before checking for errors
	if err != nil {
		log.Fatal(err)
	}
}
```

Example of **correct** code:

```go
func goodHTTPGet() {
	res, err := http.Get("http://foo.com")
	if err != nil {
		log.Fatal(err)
	}
	defer res.Body.Close()
}
```

## Further Reading

* [Go - Package http](https://golang.org/pkg/net/http/)
* [Go Vet - httpresponse](https://golang.org/cmd/vet/#hdr-HTTP_responses_used_incorrectly)
