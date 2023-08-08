Pattern: Unnecessary condition

Issue: -

## Description

This rule checks for unnecessary conditional expressions.

## Examples

```ruby
# bad
a = b ? b : c

# good
a = b || c
```
```ruby
# bad
if b
  b
else
  c
end

# good
b || c

# good
if b
  b
elsif cond
  c
end
```

## Further Reading

* [RuboCop - Style/UnneededCondition](https://docs.rubocop.org/rubocop/cops_style.html#styleunneededcondition)
