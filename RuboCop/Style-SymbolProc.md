Pattern: Use of symbol as block instead of proc

Issue: -

## Description

Use symbols as procs when possible.

## Examples

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
