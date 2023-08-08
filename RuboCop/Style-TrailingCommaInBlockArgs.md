Pattern: Trailing comma in block argument

Issue: -

## Description

This rule checks whether trailing commas in block arguments are
required. Blocks with only one argument and a trailing comma require
that comma to be present. Blocks with more than one argument never
require a trailing comma.

## Examples

```ruby
# bad
add { |foo, bar,| foo + bar }

 # good
add { |foo, bar| foo + bar }

# good
add { |foo,| foo }

# good
add { foo }

# bad
```

## Further Reading

* [RuboCop - Style/TrailingCommaInBlockArgs](https://docs.rubocop.org/rubocop/cops_style.html#styletrailingcommainblockargs)
