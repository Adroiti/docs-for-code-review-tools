Pattern: Redundant conditional

Issue: -

## Description

This rule checks for redundant returning of `true`/`false` in conditionals.

## Examples

```ruby
# bad
x == y ? true : false

# bad
if x == y
  true
else
  false
end

# good
x == y

# bad
x == y ? false : true

# good
x != y
```

## Further Reading

* [RuboCop - Style/RedundantConditional](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantconditional)
