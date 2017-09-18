Pattern: Duplicate gem

Issue: -

## Description

A Gem's requirements should be listed only once in a `Gemfile`.

## Examples

```ruby
# bad
gem 'rubocop'
gem 'rubocop'

# bad
group :development do
  gem 'rubocop'
end

group :test do
  gem 'rubocop'
end

# good
group :development, :test do
  gem 'rubocop'
end

# good
gem 'rubocop', groups: [:development, :test]
```

## Default configuration

Attribute | Value
--- | ---
Include | \*\*/Gemfile, \*\*/gems.rb

## Further Reading

* [RuboCop - Bundler/DuplicatedGem](https://rubocop.readthedocs.io/en/latest/cops_bundler/#bundlerduplicatedgem)
