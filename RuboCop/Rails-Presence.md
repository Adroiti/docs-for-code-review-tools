Pattern: Missing use of `Object#presence`

Issue: -

## Description

This rule checks code that can be written more easily using `Object#presence` defined by Active Support.

## Examples

```ruby
# bad
a.present? ? a : nil

# bad
!a.present? ? nil : a

# bad
a.blank? ? nil : a

# bad
!a.blank? ? a : nil

# good
a.presence
```
```ruby
# bad
a.present? ? a : b

# bad
!a.present? ? b : a

# bad
a.blank? ? b : a

# bad
!a.blank? ? a : b

# good
a.presence || b
```

## Further Reading

* [RuboCop - Rails/Presence](https://rubocop.readthedocs.io/en/latest/cops_rails/#railspresence)
