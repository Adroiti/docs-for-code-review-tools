Pattern: Rails/FindEach

Issue: -

## Description

This cop is used to identify usages of `all.each` and
change them to use `all.find_each` instead.

### Example

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

* [RuboCop - Rails/FindEach](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsfindeach)
* [https://github.com/bbatsov/rails-style-guide#find-each](https://github.com/bbatsov/rails-style-guide#find-each)
