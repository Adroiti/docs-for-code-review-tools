Pattern: Function returns too many results

Issue: -

## Description

Functions returning too many results can be hard to understand/use.

## Configuration

(int) the maximum allowed return values

## Example:

```toml
[rule.function-result-limit]
  arguments =[3]
```

## Further Reading

* [Revive - function-result-limit](https://revive.run/r#function-result-limit)