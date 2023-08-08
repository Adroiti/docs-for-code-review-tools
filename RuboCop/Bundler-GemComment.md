Pattern: Missing comment for gem 

Issue: -

## Description

Add a comment describing each gem in your Gemfile.

### Examples

```ruby
# bad

gem 'foo'

# good

# Helpers for the foo things.
gem 'foo'
```

### Configurable attributes

Name | Default value
--- | --- | ---
Include | `**/*.gemfile`, `**/Gemfile`, `**/gems.rb`
Whitelist | `[]`

## Further Reading

* [RuboCop - Bundler/GemComment](https://docs.rubocop.org/rubocop/cops_bundler.html#bundlergemcomment)
