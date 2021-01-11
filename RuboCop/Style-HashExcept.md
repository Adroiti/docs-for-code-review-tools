Pattern: Missing use of `Hash#except`

Issue: -

## Description

This rule checks for usages of `Hash#reject`, `Hash#select`, and `Hash#filter` methods that can be replaced with `Hash#except` method.

This rule should only be enabled on Ruby version 3.0 or higher. (`Hash#except` was added in Ruby 3.0.)

## Examples

```ruby
# bad
{foo: 1, bar: 2, baz: 3}.reject {|k, v| k == :bar }
{foo: 1, bar: 2, baz: 3}.select {|k, v| k != :bar }
{foo: 1, bar: 2, baz: 3}.filter {|k, v| k != :bar }

# good
{foo: 1, bar: 2, baz: 3}.except(:bar)
```

## Further Reading

* [RuboCop - Style/HashExcept](https://docs.rubocop.org/rubocop/cops_style.html#stylehashexcept)
