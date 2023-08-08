Pattern: Redundant freeze

Issue: -

## Description

This rule check for uses of `Object#freeze` on immutable objects.

## Examples

```ruby
# bad
CONST = 1.freeze

# good
CONST = 1
```

## Further Reading

* [RuboCop - Style/RedundantFreeze](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantfreeze)
