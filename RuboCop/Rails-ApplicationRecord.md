Pattern: Model not deriving from `ApplicationRecord`

Issue: -

## Description

This cop checks that models subclass `ApplicationRecord` with Rails 5.0.

### Example

```ruby
# good
class Rails5Model < ApplicationRecord
  ...
end

# bad
class Rails4Model < ActiveRecord::Base
  ...
end
```

## Further Reading

* [RuboCop - Rails/ApplicationRecord](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsapplicationrecord)
