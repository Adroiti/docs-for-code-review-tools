Pattern: Use of `Hash#keys.each`/`Hash#values.each`

Issue: -

## Description

`Hash#keys.each` allocates an array of keys; `Hash#each_key` iterates through the keys without allocating a new array.  This is the reason why `Hash#each_key` exists. The same applies to `Hash#values.each`.

## Examples

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

## Further Reading

* [RuboCop - Performance/HashEachMethods](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancehasheachmethods)
* [https://github.com/bbatsov/ruby-style-guide#hash-each](https://github.com/bbatsov/ruby-style-guide#hash-each)
* [https://github.com/JuanitoFatas/fast-ruby#stringgsub-vs-stringtr-code](https://github.com/JuanitoFatas/fast-ruby#stringgsub-vs-stringtr-code)
