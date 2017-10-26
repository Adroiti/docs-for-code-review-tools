Pattern: Uncapitalized first letter of type

Issue: -

## Description

This rule enforces that first letter of types is capitalized.

## Examples

**Pass**
```
query {
  someUnion {
    ... on SomeType {
      someField
    }
  }
}
```

**Fail**
```
query {
  someUnion {
    ... on someType {
      someField
    }
  }
}
```