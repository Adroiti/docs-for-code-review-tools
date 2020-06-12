Pattern: Missing use of `present?`

Issue: -

## Description

This rule checks for code that can be changed to `present?`.

Settings:
  _NotNilAndNotEmpty_: Convert checks for not `nil` and `not empty?`
                     to `present?`
  _NotBlank_: Convert usages of not `blank?` to `present?`
  _UnlessBlank_: Convert usages of `unless` `blank?` to `if` `present?`

## Examples

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

* [RuboCop - Rails/Present](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railspresent)
