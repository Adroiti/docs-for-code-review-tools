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

* [RuboCop - Style/LambdaCall](https://docs.rubocop.org/rubocop/cops_style.html#stylelambdacall)
* [https://github.com/bbatsov/ruby-style-guide#proc-call](https://github.com/bbatsov/ruby-style-guide#proc-call)
