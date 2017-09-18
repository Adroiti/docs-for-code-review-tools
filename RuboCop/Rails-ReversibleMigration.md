Pattern: Migration is not reversible

Issue: -

## Description

This rule checks whether the change method of the migration file is reversible.

## Examples

```ruby
# bad
def change
  change_table :users do |t|
    t.remove :name
  end
end

# good
def change
  create_table :users do |t|
    t.string :name
  end
end

# good
def change
  reversible do |dir|
    change_table :users do |t|
      dir.up do
        t.column :name, :string
      end

      dir.down do
        t.remove :name
      end
    end
  end
end
```
```ruby
# drop_table

# bad
def change
  drop_table :users
end

# good
def change
  drop_table :users do |t|
    t.string :name
  end
end
```
```ruby
# change_column_default

# bad
def change
  change_column_default(:suppliers, :qualification, 'new')
end

# good
def change
  change_column_default(:posts, :state, from: nil, to: "draft")
end
```
```ruby
# remove_column

# bad
def change
  remove_column(:suppliers, :qualification)
end

# good
def change
  remove_column(:suppliers, :qualification, :string)
end
```
```ruby
# remove_foreign_key

# bad
def change
  remove_foreign_key :accounts, column: :owner_id
end

# good
def change
  remove_foreign_key :accounts, :branches
end
```
```ruby
# change_table

# bad
def change
  change_table :users do |t|
    t.remove :name
    t.change_default :authorized, 1
    t.change :price, :string
  end
end

# good
def change
  change_table :users do |t|
    t.string :name
  end
end

# good
def change
  reversible do |dir|
    change_table :users do |t|
      dir.up do
        t.change :price, :string
      end

      dir.down do
        t.change :price, :integer
      end
    end
  end
end
```

## Default configuration

Attribute | Value
--- | ---
Include | db/migrate/\*.rb

## Further Reading

* [RuboCop - Rails/ReversibleMigration](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsreversiblemigration)
* [https://github.com/bbatsov/rails-style-guide#reversible-migration](https://github.com/bbatsov/rails-style-guide#reversible-migration)
* [http://api.rubyonrails.org/classes/ActiveRecord/Migration/CommandRecorder.html](http://api.rubyonrails.org/classes/ActiveRecord/Migration/CommandRecorder.html)
