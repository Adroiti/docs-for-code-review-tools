Pattern: Useless comparison with itself

Issue: -

## Description

This rule checks for comparison of something with itself.

## Examples

```ruby
# bad

x.top >= x.top
```

## Further Reading

* [RuboCop - Lint/UselessComparison](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintuselesscomparison)
