Pattern: Non-standard signatures for methods with familiar names

Issue: -

## Description

This rule enforces signature use of common methods with these names:

```
Format GobEncode GobDecode MarshalJSON MarshalXML
Peek ReadByte ReadFrom ReadRune Scan Seek
UnmarshalJSON UnreadByte UnreadRune WriteByte
WriteTo
```
Because the checks are dynamic, such methods would not cause a compile error if they have the wrong signature: instead the dynamic check would fail, sometimes mysteriously.


Example of **incorrect** code:

```go
type MethodTestInterface interface {
	ReadByte() byte // should have signature for bufio.Reader.ReadByte
}
```

Example of **correct** code:

```go
type MethodTestInterface interface {
	ReadByte() (byte, error)
}
```

A few of the canonical methods have very common names. For example, a type might implement a `Scan` method that has nothing to do with `fmt.Scanner`, but we still want to check the methods that are intended to implement `fmt.Scanner`. To do that, the arguments that have _a = prefix_ are treated as signals that the canonical meaning is intended: if a `Scan` method doesn't have a `fmt.ScanState` as its first argument, we let it go. But if it does have a `fmt.ScanState`, then the rest has to match.

## Further Reading

* [Go Vet - methods](https://golang.org/cmd/vet/#hdr-Methods)
