Pattern: Malformed line end concatenation

Issue: -

## Description

This cop checks for string literal concatenation at the end of a line. Use `\\` instead of `+` or `<<` to concatenate strings.

### Example

```ruby
# bad
some_str = 'one' +
           'two'

some_str = 'one' <<
           'two'

# good
some_str = 'one' \
           'two'
```

## Further Reading

* [RuboCop - Style/LineEndConcatenation](https://rubocop.readthedocs.io/en/latest/cops_style/#stylelineendconcatenation)
