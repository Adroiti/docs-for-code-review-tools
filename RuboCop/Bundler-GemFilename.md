Pattern: Malformed Gem filename

Issue: -

## Description

This rule verifies that a project contains `Gemfile` or `gems.rb` file and correct
associated lock file based on the configuration.

## Examples

#### EnforcedStyle: Gemfile (default)

```ruby
# bad
Project contains gems.rb and gems.locked files

# bad
Project contains Gemfile and gems.locked file

# good
Project contains Gemfile and Gemfile.lock
```

#### EnforcedStyle: gems.rb

```ruby
# bad
Project contains Gemfile and Gemfile.lock files

# bad
Project contains gems.rb and Gemfile.lock file

# good
Project contains gems.rb and gems.locked files
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `Gemfile` | `Gemfile`, `gems.rb`
Include | `+**/Gemfile+`, `+**/gems.rb+`, `+**/Gemfile.lock+`, `+**/gems.locked+` | Array

## Further Reading

* [RuboCop - Bundler/GemFilename](https://docs.rubocop.org/rubocop/cops_bundler.html#bundlergemfilename)
