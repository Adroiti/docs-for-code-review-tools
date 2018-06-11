Pattern: Inconsistent safe navigation

Issue: -

## Description

This rule check to make sure that if safe navigation is used for a method
call in an `&&` or `||` condition that safe navigation is used for all
method calls on that same object.

## Examples

```ruby
# bad
foo&.bar && foo.baz

# bad
foo.bar || foo&.baz

# bad
foo&.bar && (foobar.baz || foo.baz)

# good
foo.bar && foo.baz

# good
foo&.bar || foo&.baz

# good
foo&.bar && (foobar.baz || foo&.baz)
```

## Default configuration

Attribute | Value
--- | ---
Whitelist | `present?`, `blank?`, `presence`, `try`, `try!`

## Further Reading

* [RuboCop - Lint/SafeNavigationConsistency](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintsafenavigationconsistency)
