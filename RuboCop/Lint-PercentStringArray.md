Pattern: Lint/PercentStringArray

Issue: -

## Description

This cop checks for quotes and commas in %w, e.g. `%w('foo', "bar")`

It is more likely that the additional characters are unintended (for
example, mistranslating an array of literals to percent string notation)
rather than meant to be part of the resulting strings.

### Example

```ruby
# bad

%w('foo', "bar")
```
```ruby
# good

%w(foo bar)
```

## Further Reading

* [RuboCop - Lint/PercentStringArray](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintpercentstringarray)