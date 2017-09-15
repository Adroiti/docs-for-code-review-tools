Pattern: Unnecessary `:` or `,` in `%i`

Issue: -

## Description

This cop checks for colons and commas in `%i`, e.g. `%i(:foo, :bar)`

It is more likely that the additional characters are unintended (for
example, mistranslating an array of literals to percent string notation)
rather than meant to be part of the resulting symbols.

### Example

```ruby
# bad

%i(:foo, :bar)
```
```ruby
# good

%i(foo bar)
```

## Further Reading

* [RuboCop - Lint/PercentSymbolArray](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintpercentsymbolarray)
