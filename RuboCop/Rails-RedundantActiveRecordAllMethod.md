Pattern: Redundant `all` used as a receiver

Issue: -

## Description

Detects redundant `all` used as a receiver for Active Record query methods.

## Examples

```ruby
# bad
User.all.find(id)
User.all.order(:created_at)
users.all.where(id: ids)
user.articles.all.order(:created_at)

# good
User.find(id)
User.order(:created_at)
users.where(id: ids)
user.articles.order(:created_at)
```

## Further Reading

* [RuboCop - Rails/RedundantActiveRecordAllMethod](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsredundantactiverecordallmethod)
