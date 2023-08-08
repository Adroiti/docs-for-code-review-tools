Pattern: Malformed indentation of multi-line operation

Issue: -

## Description

This rule checks the indentation of the right hand side operand in binary operations that span more than one line.

## Examples

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

* [RuboCop - Layout/MultilineOperationIndentation](https://docs.rubocop.org/rubocop/cops_layout.html#layoutmultilineoperationindentation)
