Pattern: Performance/HashEachMethods

Issue: -

## Description

This cop checks for uses of `each_key` & `each_value` Hash methods.

### Example

```ruby
# bad
hash.keys.each { |k| p k }
hash.values.each { |v| p v }
hash.each { |k, _v| p k }
hash.each { |_k, v| p v }

# good
hash.each_key { |k| p k }
hash.each_value { |v| p v }
```

## Default configuration

Attribute | Value
--- | ---
AutoCorrect | false

## Further Reading

* [RuboCop - Performance/HashEachMethods](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancehasheachmethods)
* [https://github.com/bbatsov/ruby-style-guide#hash-each](https://github.com/bbatsov/ruby-style-guide#hash-each)
