Pattern: Malformed Gem version specification

Issue: -

## Description

Enforce that Gem version specifications are either required or forbidden.

### Examples

```ruby
# bad
gem 'rubocop'

# good
gem 'rubocop', '~> 1.12'

# good
gem 'rubocop', '>= 1.10.0'

# good
gem 'rubocop', '>= 1.5.0', '< 1.10.0'
```

## Further Reading

* [RuboCop - Bundler/GemVersion](https://docs.rubocop.org/rubocop/cops_bundler.html#bundlergemversion)
