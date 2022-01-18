Pattern: Missing use of schema `comment`

Issue: -

## Description

This rule enforces the use of the `comment` option when adding a new table or column to the database during a migration.

## Examples

```ruby
# bad (no comment for a new column or table)
add_column :table, :column, :integer

create_table :table do |t|
  t.type :column
end

# good
add_column :table, :column, :integer, comment: 'Number of offenses'

create_table :table, comment: 'Table of offenses data' do |t|
  t.type :column, comment: 'Number of offenses'
end
```

## Further Reading

* [RuboCop - Rails/SchemaComment](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsschemacomment)
