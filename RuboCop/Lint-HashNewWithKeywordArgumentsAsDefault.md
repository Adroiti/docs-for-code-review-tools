Pattern: Deprecated use of keyword argument in `Hash.new`

Issue: -

## Description

Checks for the deprecated use of keyword arguments as a default in `Hash.new`.

## Examples

```ruby
# bad
Hash.new(key: :value)

# good
Hash.new({key: :value})
```

## Further Reading

* [RuboCop - Lint/HashNewWithKeywordArgumentsAsDefault](https://docs.rubocop.org/rubocop/cops_lint.html#linthashnewwithkeywordargumentsasdefault)
