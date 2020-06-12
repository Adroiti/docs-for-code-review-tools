Pattern: Malfromed reflection class name

Issue: -

## Description

Checks if the value of the option `class_name`, in the definition of a reflection is a string.

### Examples

```ruby
# bad
has_many :accounts, class_name: Account
has_many :accounts, class_name: Account.name

# good
has_many :accounts, class_name: 'Account'
```

## Further Reading

* [RuboCop - Rails/ReflectionClassName](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsreflectionclassname)
