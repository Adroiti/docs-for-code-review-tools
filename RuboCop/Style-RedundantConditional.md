Pattern: Redundant conditional

Issue: -

## Description

This cop checks for redundant returning of true/false in conditionals.

### Example

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

* [RuboCop - Style/RedundantConditional](https://rubocop.readthedocs.io/en/latest/cops_style/#styleredundantconditional)
