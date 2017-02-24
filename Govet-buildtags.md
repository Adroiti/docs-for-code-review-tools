Pattern: Badly formed or misplaced +build tags

Issue: -

## Description

This rule checks if rules for build constraints, also known as a build tags, are being followed:
- should appear near the top of the file, preceded only by blank lines and other line comments
- should appear before the package clause
- have valid name and valid space-separated options

Example of **incorrect** (malformed +build name) code:

```go
// +builder linux,386 darwin,!cgo
```

Example of **correct** code:

```go
// +build linux,386 darwin,!cgo
```

## Further Reading

* [Go - Build Constraints](https://golang.org/pkg/go/build/#hdr-Build_Constraints)
* [Go Vet - buildtags](https://golang.org/cmd/vet/#hdr-Build_tags)
