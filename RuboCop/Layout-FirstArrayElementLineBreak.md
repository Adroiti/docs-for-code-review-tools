Pattern: Layout/FirstArrayElementLineBreak

Issue: -

## Description

This cop checks for a line break before the first element in a
multi-line array.

### Example

```ruby
# bad
[ :a,
  :b]

# good
[
  :a,
  :b]
```

## Further Reading

* [RuboCop - Layout/FirstArrayElementLineBreak](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutfirstarrayelementlinebreak)
