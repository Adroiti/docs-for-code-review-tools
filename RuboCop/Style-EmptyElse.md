Pattern: Empty `else` clause

Issue: -

## Description

Checks for empty `else` clauses, possibly including comments and/or an explicit `nil` depending on the enforced style.

SupportedStyles:

### Example

```ruby
# good for all styles

if condition
  statement
else
  statement
end

# good for all styles
if condition
  statement
end
```
```ruby
# empty - warn only on empty else

# bad
if condition
  statement
else
end

# good
if condition
  statement
else
  nil
end
```
```ruby
# nil - warn on else with nil in it

# bad
if condition
  statement
else
  nil
end

# good
if condition
  statement
else
end
```
```ruby
# both - warn on empty else and else with nil in it

# bad
if condition
  statement
else
  nil
end

# bad
if condition
  statement
else
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | both
SupportedStyles | empty, nil, both

## Further Reading

* [RuboCop - Style/EmptyElse](https://rubocop.readthedocs.io/en/latest/cops_style/#styleemptyelse)
