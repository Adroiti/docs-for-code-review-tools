Pattern: Unnamed operation

Issue: -

## Description

This rule validates that all operations are named. Naming operations is valuable for including in server-side logs and debugging.

## Examples

**Pass**
```
query FetchUsername {
  viewer {
    name
  }
}
```

**Fail**
```
query {
  viewer {
    name
  }
}
```