Pattern: Deprecated field as part of the query

Issue: -

## Description

Validates that no deprecated fields are part of the query. This is useful to discover fields that have been marked as deprecated and shouldn't be used.

## Examples

**Fail**
```
// 'id' requested and marked as deprecated in the schema

schema {
  query {
    viewer {
      id: Int @deprecated(reason: "Use the 'uuid' field instead")
      uuid: String
    }
  }
}

query ViewerName {
  viewer {
    id
  }
}
```