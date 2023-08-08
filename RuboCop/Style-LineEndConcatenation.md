Pattern: Malformed line end concatenation

Issue: -

## Description

This rule checks for string literal concatenation at the end of a line. Use `\\` instead of `+` or `<<` to concatenate strings.

## Examples

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

* [RuboCop - Style/LineEndConcatenation](https://docs.rubocop.org/rubocop/cops_style.html#stylelineendconcatenation)
