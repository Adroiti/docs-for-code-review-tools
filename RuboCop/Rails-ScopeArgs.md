Pattern: Rails/ScopeArgs

Issue: -

## Description

This cop checks for scope calls where it was passed
a method (usually a scope) instead of a lambda/proc.

### Example

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
