Pattern: Missing use of `blank?`

Issue: -

## Description

This rule checks for code that can be changed to `blank?`.
Settings:
  _NilOrEmpty_: Convert checks for `nil` or `empty?` to `blank?`
  _NotPresent_: Convert usages of not `present?` to `blank?`
  _UnlessPresent_: Convert usages of `unless` `present?` to `blank?`

## Examples

```ruby
# NilOrEmpty: true
  # bad
  foo.nil? || foo.empty?
  foo == nil || foo.empty?

  # good
  foo.blank?

# NotPresent: true
  # bad
  !foo.present?

  # good
  foo.blank?

# UnlessPresent: true
  # bad
  something unless foo.present?
  unless foo.present?
    something
  end

  # good
  something if foo.blank?
  if foo.blank?
    something
  end
```

## Default configuration

Attribute | Value
--- | ---
NilOrEmpty | true
NotPresent | true
UnlessPresent | true

## Further Reading

* [RuboCop - Rails/Blank](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsblank)
