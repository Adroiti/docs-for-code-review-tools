Pattern: Slow array flattening

Issue: -

## Description

This rule is used to identify usages of slow array flattening.

## Examples

```ruby
# bad
[1, 2, 3, 4].map { |e| [e, e] }.flatten(1)
[1, 2, 3, 4].collect { |e| [e, e] }.flatten(1)

# good
[1, 2, 3, 4].flat_map { |e| [e, e] }
[1, 2, 3, 4].map { |e| [e, e] }.flatten
[1, 2, 3, 4].collect { |e| [e, e] }.flatten
```

## Default configuration

Attribute | Value
--- | ---
EnabledForFlattenWithoutParams | false

## Further Reading

* [RuboCop - Performance/FlatMap](https://rubocop.readthedocs.io/en/latest/cops_performance/#performanceflatmap)
* [https://github.com/JuanitoFatas/fast-ruby#enumerablemaparrayflatten-vs-enumerableflat_map-code](https://github.com/JuanitoFatas/fast-ruby#enumerablemaparrayflatten-vs-enumerableflat_map-code)
