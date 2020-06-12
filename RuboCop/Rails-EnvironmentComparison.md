Pattern: Missing use of `Rails.env.%<env>s?`

Issue: -

## Description

This rule checks that `Rails.env` is compared using `.production?`-like methods instead of equality against a string or symbol.

## Examples

```ruby
# bad
Rails.env == 'production'

# bad, always returns false
Rails.env == :test

# good
Rails.env.production?
```

## Further Reading

* [RuboCop - Rails/EnvironmentComparison](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsenvironmentcomparison)
