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

* [RuboCop - Lint/RedundantWithIndex](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintredundantwithindex)
