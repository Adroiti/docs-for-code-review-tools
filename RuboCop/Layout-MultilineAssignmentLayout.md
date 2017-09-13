Pattern: Layout/MultilineAssignmentLayout

Issue: -

## Description

This cop checks whether the multiline assignments have a newline
after the assignment operator.

### Example

```ruby
# bad (with EnforcedStyle set to new_line)
foo = if expression
  'bar'
end

# good (with EnforcedStyle set to same_line)
foo = if expression
  'bar'
end

# good (with EnforcedStyle set to new_line)
foo =
  if expression
    'bar'
  end

# good (with EnforcedStyle set to new_line)
foo =
  begin
    compute
  rescue => e
    nil
  end
```

## Default configuration

Attribute | Value
--- | ---
SupportedTypes | block, case, class, if, kwbegin, module
EnforcedStyle | new_line
SupportedStyles | same_line, new_line

## Further Reading

* [RuboCop - Layout/MultilineAssignmentLayout](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutmultilineassignmentlayout)
* [https://github.com/bbatsov/ruby-style-guide#indent-conditional-assignment](https://github.com/bbatsov/ruby-style-guide#indent-conditional-assignment)
