Pattern: Performance/RedundantSortBy

Issue: -

## Description

This cop identifies places where `sort_by { ... }` can be replaced by
`sort`.

### Example

```ruby
# bad
array.sort_by { |x| x }
array.sort_by do |var|
  var
end

# good
array.sort
```

## Further Reading

* [RuboCop - Performance/RedundantSortBy](https://rubocop.readthedocs.io/en/latest/cops_performance/#performanceredundantsortby)
