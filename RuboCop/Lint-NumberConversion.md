Pattern: Unsafe number conversion

Issue: -

## Description

Unsafe number conversion can cause unexpected error if auto type conversion fails. Prefer parsing with number class instead.

## Examples

```ruby
# bad

'10'.to_i
'10.2'.to_f
'10'.to_c

# good

Integer('10', 10)
Float('10.2')
Complex('10')
```

## Further Reading

* [RuboCop - Lint/NumberConversion](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintnumberconversion)
