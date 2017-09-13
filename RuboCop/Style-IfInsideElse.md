Pattern: Style/IfInsideElse

Issue: -

## Description

If the `else` branch of a conditional consists solely of an `if` node,
it can be combined with the `else` to become an `elsif`.
This helps to keep the nesting level from getting too deep.

### Example

```ruby
# good
if condition_a
  action_a
elsif condition_b
  action_b
else
  action_c
end

# bad
if condition_a
  action_a
else
  if condition_b
    action_b
  else
    action_c
  end
end
```

## Further Reading

* [RuboCop - Style/IfInsideElse](https://rubocop.readthedocs.io/en/latest/cops_style/#styleifinsideelse)
