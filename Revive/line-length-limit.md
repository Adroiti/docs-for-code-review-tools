Pattern: Line is too long

Issue: -

## Description

Warns in the presence of code lines longer than a configured maximum.

## Configuration

(int) maximum line length in characters.

## Example:

```toml
[rule.line-length-limit]
  arguments =[80]
```

## Further Reading

* [Revive - line-length-limit](https://revive.run/r#line-length-limit)