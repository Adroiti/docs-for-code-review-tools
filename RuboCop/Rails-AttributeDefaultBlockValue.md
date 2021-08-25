Pattern: Missing method in a block to `:default` option

Issue: -

## Description

Looks for `attribute` class methods that specify a `:default` option which value is an array, string literal or method call without a block. It will accept all other values, such as string, symbol, integer and float literals as well as constants.

## Examples

```ruby
# bad
class User < ApplicationRecord
  attribute :confirmed_at, :datetime, default: Time.zone.now
end

# good
class User < ApplicationRecord
  attribute :confirmed_at, :datetime, default: -> { Time.zone.now }
end

# bad
class User < ApplicationRecord
  attribute :roles, :string, array: true, default: []
end

# good
class User < ApplicationRecord
  attribute :roles, :string, array: true, default: -> { [] }
end

# bad
class User < ApplicationRecord
  attribute :configuration, default: {}
end

# good
class User < ApplicationRecord
  attribute :configuration, default: -> { {} }
end

# good
class User < ApplicationRecord
  attribute :role, :string, default: :customer
end

# good
class User < ApplicationRecord
  attribute :activated, :boolean, default: false
end

# good
class User < ApplicationRecord
  attribute :login_count, :integer, default: 0
end

# good
class User < ApplicationRecord
  FOO = 123
  attribute :custom_attribute, :integer, default: FOO
end
```

## Further Reading

* [RuboCop - Rails/AttributeDefaultBlockValue](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsattributedefaultblockvalue)
