Pattern: Missing use of `any`

Issue: -

## Description

Since GO 1.18, `interface{}` has an alias: `any`. This rule proposes to replace instances of `interface{}` with `any`.

## Further Reading

* [Revive - use-any](https://revive.run/r#use-any)