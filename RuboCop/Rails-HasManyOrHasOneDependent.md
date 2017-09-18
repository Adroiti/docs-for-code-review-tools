Pattern: Missing `:dependent` option for `has_many`/`has_one`

Issue: -

## Description

This cop looks for `has_many` or `has_one` associations that don't specify a `:dependent` option.

### Example

```ruby
# bad
class User < ActiveRecord::Base
  has_many :comments
  has_one :avatar
end

# good
class User < ActiveRecord::Base
  has_many :comments, dependent: :restrict_with_exception
  has_one :avatar, dependent: :destroy
end
```

## Default configuration

Attribute | Value
--- | ---
Include | app/models/\*\*/\*.rb

## Further Reading

* [RuboCop - Rails/HasManyOrHasOneDependent](https://rubocop.readthedocs.io/en/latest/cops_rails/#railshasmanyorhasonedependent)
* [https://github.com/bbatsov/rails-style-guide#has_many-has_one-dependent-option](https://github.com/bbatsov/rails-style-guide#has_many-has_one-dependent-option)
