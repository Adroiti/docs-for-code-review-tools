Pattern: Use of `where.first` instead of `find_by`

Issue: -

## Description

This rule is used to identify usages of `where.first` and change them to use `find_by` instead.

## Examples

```ruby
# bad
User.where(name: 'Bruce').first
User.where(name: 'Bruce').take

# good
User.find_by(name: 'Bruce')
```

## Default configuration

Attribute | Value
--- | ---
Include | app/models/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/FindBy](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsfindby)
* [https://github.com/bbatsov/rails-style-guide#find_by](https://github.com/bbatsov/rails-style-guide#find_by)
