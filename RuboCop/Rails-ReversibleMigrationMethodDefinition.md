Pattern: Missing use of `change` or `up`/`down` for migration

Issue: -

## Description

Checks whether the migration implements either a `change` method or both an `up` and a `down` method.

## Examples

```ruby
# bad
class SomeMigration < ActiveRecord::Migration[6.0]
  def up
    # up migration
  end

  # <----- missing down method
end

class SomeMigration < ActiveRecord::Migration[6.0]
  # <----- missing up method

  def down
    # down migration
  end
end

# good
class SomeMigration < ActiveRecord::Migration[6.0]
  def change
    # reversible migration
  end
end

# good
class SomeMigration < ActiveRecord::Migration[6.0]
  def up
    # up migration
  end

  def down
    # down migration
  end
end
```

## Further Reading

* [RuboCop - Rails/ReversibleMigrationMethodDefinition](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsreversiblemigrationmethoddefinition)
