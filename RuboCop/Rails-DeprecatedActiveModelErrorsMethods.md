Pattern: Use of deprecated `ActiveModel#errors`

Issue: -

## Description

This rule checks direct manipulation of `ActiveModel#errors` as hash.
These operations are deprecated in Rails 6.1 and will not work in Rails 7.

## Examples

```ruby
# bad
user.errors[:name] << 'msg'
user.errors.messages[:name] << 'msg'

# good
user.errors.add(:name, 'msg')

# bad
user.errors[:name].clear
user.errors.messages[:name].clear

# good
user.errors.delete(:name)
```

## Further Reading

* [Rails - Rails/DeprecatedActiveModelErrorsMethods](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdeprecatedactivemodelerrorsmethods)
