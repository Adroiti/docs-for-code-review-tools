Pattern: Redundant `with_index`

Issue: -

## Description

This rule checks for redundant `with_index`.

## Examples

```ruby
# bad
ary.each_with_index do |v|
  v
end

# good
ary.each do |v|
  v
end

# bad
ary.each.with_index do |v|
  v
end

# good
ary.each do |v|
  v
end
```

## Further Reading

* [RuboCop - Lint/RedundantWithIndex](https://docs.rubocop.org/rubocop/cops_lint.html#lintredundantwithindex)
