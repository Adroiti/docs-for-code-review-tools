Pattern: Line end concatenation

Issue: -

## Description

This cop checks for string literal concatenation at
the end of a line.

### Example

```ruby
# bad
some_str = 'ala' +
           'bala'

some_str = 'ala' <<
           'bala'

# good
some_str = 'ala' \
           'bala'
```

## Further Reading

* [RuboCop - Style/LineEndConcatenation](https://rubocop.readthedocs.io/en/latest/cops_style/#stylelineendconcatenation)
