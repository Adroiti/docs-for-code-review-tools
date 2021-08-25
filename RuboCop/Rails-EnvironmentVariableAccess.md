Pattern: Use of direct access to `ENV`

Issue: -

## Description

Looks for direct access to environment variables through the `ENV` variable within the application code. This can lead to runtime errors due to misconfiguration that could have been discovered at boot time if the environment variables were loaded as part of initialization and copied into the application’s configuration or secrets.

## Examples

```ruby
# good
Rails.application.config.foo
Rails.application.config.x.foo.bar
Rails.application.secrets.foo
Rails.application.config.foo = "bar"

# AllowReads: false (default)
# bad
ENV["FOO"]
ENV.fetch("FOO")

# AllowReads: true
# good
ENV["FOO"]
ENV.fetch("FOO")
```

## Further Reading

* [RuboCop - Rails/EnvironmentVariableAccess](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsenvironmentvariableaccess)
