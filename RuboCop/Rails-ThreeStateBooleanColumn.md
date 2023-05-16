Pattern: Malformed three state boolean

Issue: -

## Description

Enforces that boolean columns are created with default values (`false` or `true`) and
`NOT NULL` constraint.

## Examples

```ruby
# bad
add_column :users, :active, :boolean
t.column :active, :boolean
t.boolean :active

# good
add_column :users, :active, :boolean, default: true, null: false
t.column :active, :boolean, default: true, null: false
t.boolean :active, default: true, null: false
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Include | `+db/**/*.rb+` | Array

## Further Reading

* [Rails - Rails/ThreeStateBooleanColumn](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsthreestatebooleancolumn)
