Pattern: Duplicate value in enum declaration

Issue: -

## Description

This rule looks for duplicate values in enum declarations.

## Examples

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

* [RuboCop - Rails/EnumUniqueness](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsenumuniqueness)
