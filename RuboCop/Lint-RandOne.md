Pattern: Use of `rand(1)`

Issue: -

## Description

This rule checks for `rand(1)` calls. Such calls always return `0`.

## Examples

```ruby
# bad
rand 1
Kernel.rand(-1)
rand 1.0
rand(-1.0)
```
```ruby
# good
0 # just use 0 instead
```

## Further Reading

* [RuboCop - Lint/RandOne](https://docs.rubocop.org/rubocop/cops_lint.html#lintrandone)
