Pattern: Use of dynamic `find_by_*`

Issue: -

## Description

This rule checks dynamic `find_by_*` methods. Use `find_by` instead of dynamic method.

## Examples

```ruby
# bad
User.find_by_name(name)

# bad
User.find_by_name_and_email(name)

# bad
User.find_by_email!(name)

# good
User.find_by(name: name)

# good
User.find_by(name: name, email: email)

# good
User.find_by!(email: email)
```

## Default configuration

Attribute | Value
--- | ---
Whitelist | find_by_sql

## Further Reading

* [RuboCop - Rails/DynamicFindBy](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdynamicfindby)
* [https://github.com/bbatsov/rails-style-guide#find_by](https://github.com/bbatsov/rails-style-guide#find_by)
