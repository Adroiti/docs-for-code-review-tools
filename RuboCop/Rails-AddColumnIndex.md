Pattern: Use of `add_column` with `index` key

Issue: -

## Description

Checks for migrations using `add_column` that have an `index` key. `add_column` does not accept `index`, but also does not raise an error for extra keys, so it is possible to mistakenly add the key without realizing it will not actually add an index.

## Examples

```ruby
# bad (will not add an index)
add_column :table, :column, :integer, index: true

# good
add_column :table, :column, :integer
add_index :table, :column
```

## Further Reading

* [RuboCop - Rails/AddColumnIndex](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsaddcolumnindex)
