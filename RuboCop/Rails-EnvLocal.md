Pattern: Missing use of `Rails.env.local?`

Issue: -

## Description

Checks for usage of `Rails.env.development? || Rails.env.test?` which can be replaced with `Rails.env.local?`, introduced in Rails 7.1.

## Examples

```ruby
# bad
Rails.env.development? || Rails.env.test?

# good
Rails.env.local?
```

## Further Reading

* [Rails - Rails/EnvLocal](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsenvlocal)
