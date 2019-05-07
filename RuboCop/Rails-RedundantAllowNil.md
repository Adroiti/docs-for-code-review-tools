Pattern: Redundant `allow_nil`

Issue: -

## Description

Checks Rails model validations for a redundant `allow_nil` when `allow_blank` is present.

## Examples

```ruby
# bad
validates :x, length: { is: 5 }, allow_nil: true, allow_blank: true

# bad
validates :x, length: { is: 5 }, allow_nil: false, allow_blank: true

# bad
validates :x, length: { is: 5 }, allow_nil: false, allow_blank: false

# good
validates :x, length: { is: 5 }, allow_blank: true

# good
validates :x, length: { is: 5 }, allow_blank: false

# good
# Here, `nil` is valid but `''` is not
validates :x, length: { is: 5 }, allow_nil: true, allow_blank: false
```

## Configurable attributes

Name | Default value
--- | ---
Include | `app/models/**/*.rb`

## Further Reading

* [RuboCop - Rails/RedundantAllowNil](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsredundantallownil)
