Pattern: Layout/FirstParameterIndentation

Issue: -

## Description

This cop checks the indentation of the first parameter in a method call.
Parameters after the first one are checked by Style/AlignParameters, not
by this cop.

### Example

```ruby
# bad
some_method(
first_param,
second_param)

# good
some_method(
  first_param,
second_param)
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | special_for_inner_method_call_in_parentheses
SupportedStyles | consistent, special_for_inner_method_call, special_for_inner_method_call_in_parentheses
IndentationWidth |

## Further Reading

* [RuboCop - Layout/FirstParameterIndentation](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutfirstparameterindentation)
