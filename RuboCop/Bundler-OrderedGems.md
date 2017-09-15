Pattern: Unordered gems

Issue: -

## Description

Gems should be alphabetically sorted within groups.

### Example

```ruby
# bad
gem 'rubocop'
gem 'rspec'

# good
gem 'rspec'
gem 'rubocop'

# good
gem 'rubocop'

gem 'rspec'

# good only if TreatCommentsAsGroupSeparators is true
# For code quality
gem 'rubocop'
# For tests
gem 'rspec'
```

## Default configuration

Attribute | Value
--- | ---
Include | \*\*/Gemfile, \*\*/gems.rb
TreatCommentsAsGroupSeparators | true

## Further Reading

* [RuboCop - Bundler/OrderedGems](https://rubocop.readthedocs.io/en/latest/cops_bundler/#bundlerorderedgems)
