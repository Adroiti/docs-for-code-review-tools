Pattern: Struct field tags do not have canonical format

Issue: -

## Description

Struct tags that do not follow the format understood by `reflect.StructTag.Get`. Well-known encoding struct tags (json, xml) used with unexported fields.

## Further Reading

* [Go Vet - structtags](https://golang.org/cmd/vet/#hdr-Struct_field_tags_do_not_have_canonical_format)