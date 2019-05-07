Pattern: Missing line break for multi-line hash key

Issue: -

## Description

Ensures that each key in a multi-line hash starts on a separate line.

## Examples

```ruby
# bad
{
  a: 1, b: 2,
  c: 3
}

# good
{
  a: 1,
  b: 2,
  c: 3
}
```

## Further Reading

* [RuboCop - Layout/MultilineHashKeyLineBreaks](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutmultilinehashkeylinebreaks)
