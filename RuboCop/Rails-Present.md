Pattern: Rails/Present

Issue: -

## Description

This cops checks for code that can be changed to `blank?`.
Settings:
  NotNilAndNotEmpty: Convert checks for not `nil` and `not empty?`
                     to `present?`
  NotBlank: Convert usages of not `blank?` to `present?`
  UnlessBlank: Convert usages of `unless` `blank?` to `if` `present?`

### Example

```ruby
# NotNilAndNotEmpty: true
  # bad
  !foo.nil? && !foo.empty?
  foo != nil && !foo.empty?
  !foo.blank?

  # good
  foo.present?

# NotBlank: true
  # bad
  !foo.blank?
  not foo.blank?

  # good
  foo.present?

# UnlessBlank: true
  # bad
  something unless foo.blank?

  # good
  something if  foo.present?
```

## Default configuration

Attribute | Value
--- | ---
NotNilAndNotEmpty | true
NotBlank | true
UnlessBlank | true

## Further Reading

* [RuboCop - Rails/Present](https://rubocop.readthedocs.io/en/latest/cops_rails/#railspresent)
