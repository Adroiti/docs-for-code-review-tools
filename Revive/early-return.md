Pattern: Missing use of early return

Issue: -

## Description

In GO it is idiomatic to minimize nesting statements, a typical example is to avoid if-then-else constructions. This rule spots constructions like
```go
if cond {
  // do something
} else {
  // do other thing
  return ...
}
```
that can be rewritten into more idiomatic:
```go
if ! cond {
  // do other thing
  return ...
}

// do something
```

## Further Reading

* [Revive - early-return](https://revive.run/r#early-return)