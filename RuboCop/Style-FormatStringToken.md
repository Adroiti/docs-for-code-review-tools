Pattern: Inconsistent style for format string token

Issue: -

## Description

Use a consistent style for named format string tokens.

### Example

```ruby
EnforcedStyle: annotated

# bad

format('%{greeting}', greeting: 'Hello')
format('%s', 'Hello')

# good

format('%<greeting>s', greeting: 'Hello')
```
```ruby
EnforcedStyle: template

# bad

format('%<greeting>s', greeting: 'Hello')
format('%s', 'Hello')

# good

format('%{greeting}', greeting: 'Hello')
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | annotated
SupportedStyles | annotated, template

## Further Reading

* [RuboCop - Style/FormatStringToken](https://rubocop.readthedocs.io/en/latest/cops_style/#styleformatstringtoken)
