Pattern: Malformed required field

Issue: -

## Description

This rule validates that any specified required field is part of the query, but only if that field is available in schema. This is useful to ensure that query results are cached properly in the client.

## Examples

**Pass**
```
// 'uuid' required and present in the schema

schema {
  query {
    viewer {
      name
      uuid
    }
  }
}

query ViewerName {
  viewer {
    name
    uuid
  }
}
```

**Pass**
```
// 'uuid' usually required but not present in the schema here

schema {
  query {
    viewer {
      name
    }
  }
}

query ViewerName {
  viewer {
    name
  }
}
```

**Fail**
```
// 'uuid' required and present in the schema

schema {
  query {
    viewer {
      uuid
      name
    }
  }
}

query ViewerName {
  viewer {
    name
  }
}
```