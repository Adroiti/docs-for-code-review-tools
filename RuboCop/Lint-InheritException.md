Pattern: Inheritance from `Exception`

Issue: -

## Description

This cop looks for error classes inheriting from `Exception`
and its standard library subclasses, excluding subclasses of
`StandardError`. It is configurable to suggest using either
`RuntimeError` (default) or `StandardError` instead.

### Example

```ruby
# bad

class C < Exception; end
```
```ruby
# EnforcedStyle: runtime_error (default)

# good

class C < RuntimeError; end
```
```ruby
# EnforcedStyle: standard_error

# good

class C < StandardError; end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | runtime_error
SupportedStyles | runtime_error, standard_error

## Further Reading

* [RuboCop - Lint/InheritException](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintinheritexception)
