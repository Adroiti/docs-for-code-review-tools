Pattern: Redundant `with_object`

Issue: -

## Description

This rule checks for redundant `with_object`.

## Examples

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

* [RuboCop - Lint/RedundantWithObject](https://docs.rubocop.org/rubocop/cops_lint.html#lintredundantwithobject)
