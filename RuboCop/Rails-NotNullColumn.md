Pattern: `NOT NULL` column without default value

Issue: -

## Description

This rule checks for `add_column` call with `NOT NULL` constraint in migration file.

## Examples

```ruby
# bad
add_column :users, :name, :string, null: false
add_reference :products, :category, null: false

# good
add_column :users, :name, :string, null: true
add_column :users, :name, :string, null: false, default: ''
add_reference :products, :category
add_reference :products, :category, null: false, default: 1
```

## Default configuration

Attribute | Value
--- | ---
Include | db/migrate/\*.rb

## Further Reading

* [RuboCop - Rails/NotNullColumn](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsnotnullcolumn)
