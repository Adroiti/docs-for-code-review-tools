Pattern: Misaligned parameter of multi-line method

Issue: -

## Description

This rule checks if the parameters on a multi-line method call or definition are aligned.

## Examples

```ruby
# EnforcedStyle: with_first_parameter

# good

foo :bar,
    :baz

# bad

foo :bar,
  :baz
```
```ruby
# EnforcedStyle: with_fixed_indentation

# good

foo :bar,
  :baz

# bad

foo :bar,
    :baz
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | with_first_parameter
SupportedStyles | with_first_parameter, with_fixed_indentation
IndentationWidth |

## Further Reading

* [RuboCop - Layout/ParameterAlignment](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutparameteralignment)
* [https://github.com/bbatsov/ruby-style-guide#no-double-indent](https://github.com/bbatsov/ruby-style-guide#no-double-indent)
