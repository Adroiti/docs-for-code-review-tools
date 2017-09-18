Pattern: Redundant `sort_by { ... }`

Issue: -

## Description

This rule identifies places where `sort_by { ... }` can be replaced by `sort`.

## Examples

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
* [https://github.com/JuanitoFatas/fast-ruby#enumerablesort-vs-enumerablesort_by-code](https://github.com/JuanitoFatas/fast-ruby#enumerablesort-vs-enumerablesort_by-code)
