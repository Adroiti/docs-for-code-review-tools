Pattern: Inconsistent use of `to_fs`/`to_formatted_s`

Issue: -

## Description

Checks for consistent uses of `to_fs` or `to_formatted_s`, depending on the cop's configuration.

## Examples

#### EnforcedStyle: to_fs (default)

```ruby
# bad
time.to_formatted_s(:db)

# good
time.to_fs(:db)
```

#### EnforcedStyle: to_formatted_s

```ruby
# bad
time.to_fs(:db)

# good
time.to_formatted_s(:db)
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `to_fs` | `to_fs`, `to_formatted_s`

## Further Reading

* [Rails - Rails/ToFormattedS](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railstoformatteds)
* https://rails.rubystyle.guide/#prefer-to-fs