Pattern: Duplicate value in enum declaration

Issue: -

## Description

This cop looks for duplicate values in enum declarations.

### Example

```ruby
# bad
enum status: { active: 0, archived: 0 }

# good
enum status: { active: 0, archived: 1 }

# bad
enum status: [:active, :archived, :active]

# good
enum status: [:active, :archived]
```

## Default configuration

Attribute | Value
--- | ---
Include | app/models/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/EnumUniqueness](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsenumuniqueness)
