Pattern: Use of `where.first` instead of `find_by`

Issue: -

## Description

This rule enforces that `ActiveRecord#find` is used instead of `where.take!`, `find_by!`, and `find_by_id!` to retrieve a single record by primary key when you expect it to be found.

## Examples

```ruby
# bad
User.where(id: id).take!
User.find_by_id!(id)
User.find_by!(id: id)

# good
User.find(id)
```

## Further Reading

* [RuboCop - Rails/FindById](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsfindbyid)
