Pattern: Inconsistent lambda call syntax

Issue: -

## Description

This cop checks for use of the `lambda.(args)` syntax.

### Example

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
