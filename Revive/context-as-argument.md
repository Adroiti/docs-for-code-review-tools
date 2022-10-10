Pattern: Inconsistent `context.Context` usage as parameter

Issue: -

## Description

By [convention](https://github.com/golang/go/wiki/CodeReviewComments#contexts), `context.Context` should be the first parameter of a function. This rule spots function declarations that do not follow the convention.

## Configuration

* `allowTypesBefore` : (string) comma-separated list of types that may be before 'context.Context'

## Example:

```toml
[rule.context-as-argument]
  arguments = [{allowTypesBefore = "*testing.T,*github.com/user/repo/testing.Harness"}]
```

## Further Reading

* [Revive - context-as-argument](https://revive.run/r#context-as-argument)