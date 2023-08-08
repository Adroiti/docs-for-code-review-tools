Pattern: Unmerged nested conditions

Issue: -

## Description

If the branch of a conditional consists solely of a conditional node,
its conditions can be combined with the conditions of the outer branch.
This helps to keep the nesting level from getting too deep.

## Examples

```ruby
# bad
if condition_a
  if condition_b
    do_something
  end
end

# good
if condition_a && condition_b
  do_something
end
```

#### AllowModifier: false (default)

```ruby
# bad
if condition_a
  do_something if condition_b
end
```

#### AllowModifier: true

```ruby
# good
if condition_a
  do_something if condition_b
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AllowModifier | `false` | Boolean

## Further Reading

* [RuboCop - Style/SoleNestedConditional](https://docs.rubocop.org/rubocop/cops_style.html#stylesolenestedconditional)
