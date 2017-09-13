Pattern: Lint/RandOne

Issue: -

## Description

This cop checks for `rand(1)` calls.
Such calls always return `0`.

### Example

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

* [RuboCop - Lint/RandOne](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintrandone)
