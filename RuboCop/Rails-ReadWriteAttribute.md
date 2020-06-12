Pattern: Use of `read_attribute`/`write_attribute`

Issue: -

## Description

This rule checks for the use of the `read_attribute` or `write_attribute` methods.

## Examples

```ruby
# bad
x = read_attribute(:attr)
write_attribute(:attr, val)

# good
x = self[:attr]
self[:attr] = val
```

## Default configuration

Attribute | Value
--- | ---
Include | app/models/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/ReadWriteAttribute](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsreadwriteattribute)
* [https://github.com/bbatsov/rails-style-guide#read-attribute](https://github.com/bbatsov/rails-style-guide#read-attribute)
