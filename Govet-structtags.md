Pattern: Struct field tags do not have canonical format

Issue: -

## Description

This rule checks if conventions for struct field tags are being followed:
- tags have canonical format
- json or xml tags are used correctly with unexported fields


By convention, tag strings are a concatenation of optionally space-separated key:"value" pairs. Each key is a non-empty string consisting of non-control characters other than space (U+0020 ' '), quote (U+0022 '"'), and colon (U+003A ':'). Each value is quoted using U+0022 '"' characters and Go string literal syntax.

Example of **incorrect** code:

```go
type StructTagTest struct {
	A   int "hello"	// bad syntax for struct tag pair
}
```

Example of **correct** code:

```go
type StructTagTest struct {
	A   int
}
```

## Further Reading

* [Go - StructTag](https://golang.org/pkg/reflect/#StructTag)
* [Go Vet - structtags](https://golang.org/cmd/vet/#hdr-Struct_tags)
