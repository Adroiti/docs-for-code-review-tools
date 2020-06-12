Pattern: Use of `each` instead of `find_each`

Issue: -

## Description

This rule is used to identify usages of `each` and change them to use `find_each` instead. Looping through a collection of records from the database (using the `all` method, for example) is very inefficient since it will try to instantiate all the objects at once. In that case, batch processing methods allow you to work with the records in batches, thereby greatly reducing memory consumption.

## Examples

```ruby
# bad
User.all.each

# good
User.all.find_each
```

## Default configuration

Attribute | Value
--- | ---
Include | app/models/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/FindEach](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsfindeach)
* [https://github.com/bbatsov/rails-style-guide#find-each](https://github.com/bbatsov/rails-style-guide#find-each)
