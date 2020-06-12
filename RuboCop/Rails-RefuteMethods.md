Pattern: Use of `refute` instead of `assert_not` methods

Issue: -

## Description

Use `assert_not` methods instead of `refute` methods.

## Examples

```ruby
# bad
refute false
refute_empty [1, 2, 3]
refute_equal true, false

# good
assert_not false
assert_not_empty [1, 2, 3]
assert_not_equal true, false
```

## Default configuration

Attribute | Value
--- | ---
Include | `**/test/**/*`

## Further Reading

* [RuboCop - Rails/RefuteMethods](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsrefutemethods)
