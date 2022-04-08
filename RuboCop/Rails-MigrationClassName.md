Pattern: Malformed migration class name

Issue: -

## Description

This rule makes sure that each migration file defines a migration class whose name matches the file name. (e.g. `20220224111111_create_users.rb` should define `CreateUsers` class.)

## Examples

```ruby
# db/migrate/20220224111111_create_users.rb

# bad
class SellBooks < ActiveRecord::Migration[7.0]
end

# good
class CreateUsers < ActiveRecord::Migration[7.0]
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Include | `+db/migrate/*.rb+` | Array

## Further Reading

* [Rails - Rails/MigrationClassName](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsmigrationclassname)
