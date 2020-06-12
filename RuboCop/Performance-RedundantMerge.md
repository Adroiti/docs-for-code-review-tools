Pattern: Missing use of `Hash#[]=`

Issue: -

## Description

This rule identifies places where `Hash#merge!` can be replaced by `Hash#[]=`.

## Examples

```ruby
hash.merge!(a: 1)
hash.merge!({'key' => 'value'})
hash.merge!(a: 1, b: 2)
```

## Default configuration

Attribute | Value
--- | ---
MaxKeyValuePairs | 2

## Further Reading

* [RuboCop - Performance/RedundantMerge](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceredundantmerge)
* [https://github.com/JuanitoFatas/fast-ruby#hashmerge-vs-hash-code](https://github.com/JuanitoFatas/fast-ruby#hashmerge-vs-hash-code)
