Pattern: Unkeyed composite literals

Issue: -

## Description

This rule enforces field-keyed syntax over unkeyed syntax for composite struct literals. It may sometimes result in slightly more code, but offers a good trade-off in terms of maintenance:
- does not need to have an element for each struct field. Omitted fields get the zero value for that field;
- does not neeed to follow the order in which the fields are declared;
- may improve code clarity due to explicit use of key names.

Example of **incorrect** code:

```go
var badStructLiteral = flag.Flag{
	"Name",
	"Usage",
	nil, // Value
	"DefValue",
}
```

Example of **correct** code:

```go
var goodStructLiteral = flag.Flag{
	Name:  "Name",
	Usage: "Usage",
}
```

## Further Reading

* [Go Vet - Composite literals](https://golang.org/ref/spec#Composite_literals)
* [Go Vet - composites](https://golang.org/cmd/vet/#hdr-Unkeyed_composite_literals)
