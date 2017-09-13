Pattern: Lint/ImplicitStringConcatenation

Issue: -

## Description

This cop checks for implicit string concatenation of string literals
which are on the same line.

### Example

```ruby
# bad

array = ['Item 1' 'Item 2']
```
```ruby
# good

array = ['Item 1Item 2']
array = ['Item 1' + 'Item 2']
array = [
  'Item 1' \
  'Item 2'
]
```

## Further Reading

* [RuboCop - Lint/ImplicitStringConcatenation](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintimplicitstringconcatenation)
