Pattern: Use of `!collection.include?(obj)` instead of `collection.exclude?(obj)`

Issue: -

## Description

This rule enforces the use of `collection.exclude?(obj)` over `!collection.include?(obj)`.

## Examples

```ruby
# bad
!array.include?(2)
!hash.include?(:key)

# good
array.exclude?(2)
hash.exclude?(:key)
```

## Further Reading

* [RuboCop - Rails/NegateInclude](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsnegateinclude)
