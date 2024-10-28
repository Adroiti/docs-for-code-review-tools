Pattern: Use of string as `instance_double`

Issue: -

## Description

Do not use a string as `instance_double` constant.

## Examples

```ruby
# bad
instance_double('User', name: 'John')

# good
instance_double(User, name: 'John')
```

## Further Reading

* [RSpec - RSpec/StringAsInstanceDoubleConstant](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecstringasinstancedoubleconstant)