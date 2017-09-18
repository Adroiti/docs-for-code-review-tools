Pattern: Inconsistent lambda call syntax

Issue: -

## Description

This rule checks for use of the `lambda.(args)` syntax.

## Examples

```ruby
# bad
lambda.(x, y)

# good
lambda.call(x, y)
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | call
SupportedStyles | call, braces

## Further Reading

* [RuboCop - Style/LambdaCall](https://rubocop.readthedocs.io/en/latest/cops_style/#stylelambdacall)
* [https://github.com/bbatsov/ruby-style-guide#proc-call](https://github.com/bbatsov/ruby-style-guide#proc-call)
