Pattern: Trailing inline comment

Issue: -

## Description

This rule checks for trailing inline comments.

## Examples

```ruby
# good
foo.each do |f|
  # Standalone comment
  f.bar
end

# bad
foo.each do |f|
  f.bar # Trailing inline comment
end
```

## Further Reading

* [RuboCop - Style/InlineComment](https://rubocop.readthedocs.io/en/latest/cops_style/#styleinlinecomment)
