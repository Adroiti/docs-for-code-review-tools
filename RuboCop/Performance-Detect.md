Pattern: Unused `Enumerable#detect`

Issue: -

## Description

This cop is used to identify usages of
`select.first`, `select.last`, `find_all.first`, and `find_all.last`
and change them to use `detect` instead.

`ActiveRecord` compatibility:
`ActiveRecord` does not implement a `detect` method and `find` has its
own meaning. Correcting ActiveRecord methods with this cop should be
considered unsafe.

### Example

```ruby
# bad
[].select { |item| true }.first
[].select { |item| true }.last
[].find_all { |item| true }.first
[].find_all { |item| true }.last

# good
[].detect { |item| true }
[].reverse.detect { |item| true }
```

## Default configuration

Attribute | Value
--- | ---
SafeMode | true

## Further Reading

* [RuboCop - Performance/Detect](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancedetect)
* [https://github.com/JuanitoFatas/fast-ruby#enumerabledetect-vs-enumerableselectfirst-code](https://github.com/JuanitoFatas/fast-ruby#enumerabledetect-vs-enumerableselectfirst-code)
