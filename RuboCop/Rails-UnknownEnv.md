Pattern: Unknown _Rails_ environment

Issue: -

## Description

This rule checks that environments called with `Rails.env` predicates exist.

## Examples

```ruby
# bad
Rails.env.proudction?

# good
Rails.env.production?
```

## Default configuration

Attribute | Value
--- | ---
Environments | `development`, `test`, `production`

## Further Reading

* [RuboCop - Rails/UnknownEnv](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsunknownenv)
