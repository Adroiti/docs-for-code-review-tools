Pattern: Redundant freeze

Issue: -

## Description

This cop check for uses of Object#freeze on immutable objects.

### Example

```ruby
# bad
CONST = 1.freeze

# good
CONST = 1
```

## Further Reading

* [RuboCop - Style/RedundantFreeze](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantfreeze)
