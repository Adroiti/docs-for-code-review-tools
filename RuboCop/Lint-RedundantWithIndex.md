Pattern: Redundant `with_index`

Issue: -

## Description

This cop checks for redundant `with_index`.

### Example

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
