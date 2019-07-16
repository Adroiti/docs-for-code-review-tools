Pattern: Use of `assert !` instead of `assert_not`

Issue: -

## Description

This rule enforces to use `assert_not` instead of `assert !`.

## Examples

```ruby
# bad
assert !x

# good
assert_not x
```

## Default configuration

Attribute | Value
--- | ---
Include | `**/test/**/*`

## Further Reading

* [RuboCop - Rails/AssertNot](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails#railsassertnot)
