Pattern: Style/SymbolProc

Issue: -

## Description

Use symbols as procs when possible.

### Example

```ruby
# bad
something.map { |s| s.upcase }

# good
something.map(&:upcase)
```

## Default configuration

Attribute | Value
--- | ---
IgnoredMethods | respond_to, define_method

## Further Reading

* [RuboCop - Style/SymbolProc](https://rubocop.readthedocs.io/en/latest/cops_style/#stylesymbolproc)
