Pattern: Duplicate group in Gemfile

Issue: -

## Description

A Gem group, or a set of groups, should be listed only once in a Gemfile.

For example, if the values of `source`, `git`, `platforms`, or `path` surrounding `group` are different, no offense will be registered:

## Examples

```ruby
# bad
group :development do
  gem 'rubocop'
end

group :development do
  gem 'rubocop-rails'
end

# bad (same set of groups declared twice)
group :development, :test do
  gem 'rubocop'
end

group :test, :development do
  gem 'rspec'
end

# good
group :development do
  gem 'rubocop'
end

group :development, :test do
  gem 'rspec'
end

# good
gem 'rubocop', groups: [:development, :test]
gem 'rspec', groups: [:development, :test]
```

## Further Reading

* [RuboCop - Bundler/DuplicatedGroup](https://docs.rubocop.org/rubocop/cops_bundler.html#bundlerduplicatedgroup)
