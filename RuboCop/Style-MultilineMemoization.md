Pattern: Multiline memoization

Issue: -

## Description

This cop checks expressions wrapping styles for multiline memoization.

### Example

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
