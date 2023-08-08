Pattern: Missing indentation for multi-line assignment

Issue: -

## Description

This rule checks the indentation of the first line of the right-hand-side of a multi-line assignment.

## Examples

```ruby
# bad
value =
if foo
  'bar'
end

# good
value =
  if foo
    'bar'
  end
```

## Default configuration

Attribute | Value
--- | ---
IndentationWidth |

## Further Reading

* [RuboCop - Layout/AssignmentIndentation](https://docs.rubocop.org/rubocop/cops_layout.html#layoutassignmentindentation)
