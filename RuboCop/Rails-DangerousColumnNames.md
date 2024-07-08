Pattern: Dangerous column name

Issue: -

## Description

Avoid dangerous column names.

Some column names are considered dangerous because they would overwrite methods already defined.

## Examples

```ruby
# bad
add_column :users, :save

# good
add_column :users, :saved
```

## Further Reading

* [Rails - Rails/DangerousColumnNames](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdangerouscolumnnames)
