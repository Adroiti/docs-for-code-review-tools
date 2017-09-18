Pattern: Missing line break before first hash element

Issue: -

## Description

This rule checks for a line break before the first element in a multi-line hash.

## Examples

```ruby
# bad
{ a: 1,
  b: 2}

# good
{
  a: 1,
  b: 2 }
```

## Further Reading

* [RuboCop - Layout/FirstHashElementLineBreak](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutfirsthashelementlinebreak)
