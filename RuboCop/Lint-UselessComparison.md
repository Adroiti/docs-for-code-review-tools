Pattern: Lint/UselessComparison

Issue: -

## Description

This cop checks for comparison of something with itself.

### Example

```ruby
# bad

x.top >= x.top
```

## Further Reading

* [RuboCop - Lint/UselessComparison](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintuselesscomparison)
