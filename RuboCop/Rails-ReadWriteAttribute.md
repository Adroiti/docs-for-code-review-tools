Pattern: Rails/ReadWriteAttribute

Issue: -

## Description

This cop checks for the use of the read_attribute or
write_attribute methods.

### Example

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

* [RuboCop - Rails/ReadWriteAttribute](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsreadwriteattribute)
* [https://github.com/bbatsov/rails-style-guide#read-attribute](https://github.com/bbatsov/rails-style-guide#read-attribute)