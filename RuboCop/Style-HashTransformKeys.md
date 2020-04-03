Pattern: Missing use of `Hash#transform_keys`

Issue: -

## Description

This rule looks for uses of `_.each_with_object({}) {...}`,
`_.map {...}.to_h`, and `Hash[_.map {...}]` that are actually just
transforming the keys of a hash, and tries to use a simpler & faster
call to `transform_keys` instead.

This can produce false positives if we are transforming an enumerable
of key-value-like pairs that isn't actually a hash, e.g.:
`[[k1, v1], [k2, v2], ...]`

## Examples

```ruby
# bad
{a: 1, b: 2}.each_with_object({}) { |(k, v), h| h[foo(k)] = v }
{a: 1, b: 2}.map { |k, v| [k.to_s, v] }

# good
{a: 1, b: 2}.transform_keys { |k| foo(k) }
{a: 1, b: 2}.transform_keys { |k| k.to_s }
```

## Further Reading

* [RuboCop - Style/HashTransformKeys](https://rubocop.readthedocs.io/en/latest/cops_style/#stylehashtransformkeys)
