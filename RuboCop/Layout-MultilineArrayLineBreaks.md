Pattern: Missing line break for multi-line array

Issue: -

## Description

Ensures that each item in a multi-line array starts on a separate line.

## Examples

```ruby
# bad
[
  a, b,
  c
]

# good
[
  a,
  b,
  c
]
```

## Further Reading

* [RuboCop - Layout/MultilineArrayLineBreaks](https://docs.rubocop.org/rubocop/cops_layout.html#layoutmultilinearraylinebreaks)
