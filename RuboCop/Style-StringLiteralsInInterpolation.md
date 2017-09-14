Pattern: Malformed quotes in string interpolation 

Issue: -

## Description

This cop checks that quotes inside the string interpolation match the configured preference.

### Example

```ruby
# EnforcedStyle: single_quotes

# bad
result = "Tests #{success ? "PASS" : "FAIL"}"

# good
result = "Tests #{success ? 'PASS' : 'FAIL'}"
```
```ruby
# EnforcedStyle: double_quotes

# bad
result = "Tests #{success ? 'PASS' : 'FAIL'}"

# good
result = "Tests #{success ? "PASS" : "FAIL"}"
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | single_quotes
SupportedStyles | single_quotes, double_quotes

## Further Reading

* [RuboCop - Style/StringLiteralsInInterpolation](https://rubocop.readthedocs.io/en/latest/cops_style/#stylestringliteralsininterpolation)
