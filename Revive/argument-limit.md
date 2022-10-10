Pattern: Too many function arguments

Issue: -

## Description

Warns when a function receives more parameters than the maximum set by the rule's configuration.
Enforcing a maximum number of parameters helps to keep the code readable and maintainable.

## Configuration

(int) the maximum number of parameters allowed per function.

## Example:

```toml
[rule.argument-limit]
  arguments =[4]
```

## Further Reading

* [Revive - argument-limit](https://revive.run/r#argument-limit)