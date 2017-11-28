Pattern: Redundant `with_object`

Issue: -

## Description

This rule checks for redundant `with_object`.

### Example

```ruby
# bad
ary.each_with_object([]) do |v|
  v
end

# good
ary.each do |v|
  v
end

# bad
ary.each.with_object([]) do |v|
  v
end

# good
ary.each do |v|
  v
end
```

## Further Reading

* [RuboCop - Lint/RedundantWithObject](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintredundantwithobject)
