Pattern: Multi-line memoization

Issue: -

## Description

This rule checks expressions wrapping styles for multi-line memoization. Wrap blocks in `begin` and `end` instead.

## Examples

```ruby
# EnforcedStyle: keyword (default)

# bad
foo ||= (
  bar
  baz
)

# good
foo ||= begin
  bar
  baz
end
```
```ruby
# EnforcedStyle: braces

# bad
foo ||= begin
  bar
  baz
end

# good
foo ||= (
  bar
  baz
)
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | keyword
SupportedStyles | keyword, braces

## Further Reading

* [RuboCop - Style/MultilineMemoization](https://rubocop.readthedocs.io/en/latest/cops_style/#stylemultilinememoization)
