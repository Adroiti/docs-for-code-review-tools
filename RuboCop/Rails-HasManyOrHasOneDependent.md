Pattern: Missing `:dependent` option for `has_many`/`has_one`

Issue: -

## Description

This rule looks for `has_many` or `has_one` associations that don't specify a `:dependent` option.

## Examples

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

* [RuboCop - Rails/HasManyOrHasOneDependent](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails#railshasmanyorhasonedependent)
* [https://github.com/bbatsov/rails-style-guide#has_many-has_one-dependent-option](https://github.com/bbatsov/rails-style-guide#has_many-has_one-dependent-option)
