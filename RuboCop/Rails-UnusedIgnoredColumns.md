Pattern: Unused column in `ignored_columns`

Issue: -

## Description

Suggests you remove a column that does not exist in the schema from `ignored_columns`.
`ignored_columns` is necessary to drop a column from RDBMS, but you don't need it after the migration
to drop the column. You avoid forgetting to remove `ignored_columns` by this rule.

## Examples

```ruby
# bad
class User < ApplicationRecord
  self.ignored_columns = [:already_removed_column]
end

# good
class User < ApplicationRecord
  self.ignored_columns = [:still_existing_column]
end
```

## Further Reading

* [RuboCop - Rails/UnusedIgnoredColumns](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsunusedignoredcolumns)
