Pattern: Non-standard signatures for methods with familiar names

Issue: -

## Description

Non-standard signatures for methods with familiar names, including:

```
Format GobEncode GobDecode MarshalJSON MarshalXML
Peek ReadByte ReadFrom ReadRune Scan Seek
UnmarshalJSON UnreadByte UnreadRune WriteByte
WriteTo
```

## Further Reading

* [Go Vet - methods](https://golang.org/cmd/vet/#hdr-Non-standard_signatures_for_methods_with_familiar_names)