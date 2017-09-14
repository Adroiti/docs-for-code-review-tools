Pattern: Layout/MultilineOperationIndentation

Issue: -

## Description

This cop checks the indentation of the right hand side operand in
binary operations that span more than one line.

### Example

```ruby
# bad
if a +
b
  something
end

# good
if a +
   b
  something
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | aligned
SupportedStyles | aligned, indented
IndentationWidth |

## Further Reading

* [RuboCop - Layout/MultilineOperationIndentation](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutmultilineoperationindentation)