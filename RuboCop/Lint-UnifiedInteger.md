Pattern: Use of `Fixnum`/`Bignum`

Issue: -

## Description

This rule checks for using `Fixnum` or `Bignum` constant.

## Examples

```ruby
# bad

1.is_a?(Fixnum)
1.is_a?(Bignum)
```
```ruby
# good

1.is_a?(Integer)
```

## Further Reading

* [RuboCop - Lint/UnifiedInteger](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintunifiedinteger)
