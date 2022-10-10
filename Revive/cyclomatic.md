Pattern: Cyclomatic complexity is too high

Issue: -

## Description

[Cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity) is a measure of code complexity. Enforcing a maximum complexity per function helps to keep code readable and maintainable.

## Configuration

(int) the maximum function complexity

## Example:

```toml
[rule.cyclomatic]
  arguments =[3]
```

## Further Reading

* [Revive - cyclomatic](https://revive.run/r#cyclomatic)