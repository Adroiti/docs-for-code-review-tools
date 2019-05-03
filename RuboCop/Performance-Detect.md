Pattern: Missing use of `Enumerable#detect`

Issue: -

## Description

This rule is used to identify usages of `select.first`, `select.last`, `find_all.first`, and `find_all.last` and change them to use `detect` instead.

`ActiveRecord` compatibility:
`ActiveRecord` does not implement a `detect` method and `find` has its
own meaning. Correcting ActiveRecord methods with this rule should be
considered unsafe.

## Examples

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

* [RuboCop - Performance/Detect](https://github.com/rubocop-hq/rubocop-performance/blob/master/manual/cops_performance.md#performancedetect)
* [https://github.com/JuanitoFatas/fast-ruby#enumerabledetect-vs-enumerableselectfirst-code](https://github.com/JuanitoFatas/fast-ruby#enumerabledetect-vs-enumerableselectfirst-code)
