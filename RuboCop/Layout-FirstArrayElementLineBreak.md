Pattern: Missing line break before first array element

Issue: -

## Description

This rule checks for a line break before the first element in a multi-line array.

## Examples

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

* [RuboCop - Layout/FirstArrayElementLineBreak](https://docs.rubocop.org/rubocop/cops_layout.html#layoutfirstarrayelementlinebreak)
