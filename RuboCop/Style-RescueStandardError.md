Pattern: Malformed rescuing of `StandardError`

Issue: -

## Description

This rule checks for rescuing `StandardError`. There are two supported styles `implicit` and `explicit`. This rule will not register an offense if any error other than `StandardError` is specified.

## Examples

#### EnforcedStyle: implicit

```ruby
# `implicit` will enforce using `rescue` instead of
# `rescue StandardError`.

# bad
begin
  foo
rescue StandardError
  bar
end

# good
begin
  foo
rescue
  bar
end

# good
begin
  foo
rescue OtherError
  bar
end

# good
begin
  foo
rescue StandardError, SecurityError
  bar
end
```
#### EnforcedStyle: explicit (default)

```ruby
# `explicit` will enforce using `rescue StandardError`
# instead of `rescue`.

# bad
begin
  foo
rescue
  bar
end

# good
begin
  foo
rescue StandardError
  bar
end

# good
begin
  foo
rescue OtherError
  bar
end

# good
begin
  foo
rescue StandardError, SecurityError
  bar
end
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | `explicit`

## Further Reading

* [RuboCop - Style/RescueStandardError](https://rubocop.readthedocs.io/en/latest/cops_style/#stylerescuestandarderror)
