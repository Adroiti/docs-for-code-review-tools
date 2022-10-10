Pattern: Unhandled error

Issue: -

## Description

This rule warns when errors returned by a function are not explicitly handled on the caller side.

## Configuration

Function names to ignore.

## Example:

```toml
[unhandled-error]
  arguments =["fmt.Printf", "myFunction"]
```

## Further Reading

* [Revive - unhandled-error](https://revive.run/r#unhandled-error)