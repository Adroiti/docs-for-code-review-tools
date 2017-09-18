Pattern: Use of plain method call instead of `lambda`/`proc`

Issue: -

## Description

This rule checks for scope calls where it was passed
a method (usually a scope) instead of a `lambda`/`proc`.

## Examples

```ruby
# bad
scope :something, where(something: true)

# good
scope :something, -> { where(something: true) }
```

## Default configuration

Attribute | Value
--- | ---
Include | app/models/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/ScopeArgs](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsscopeargs)
