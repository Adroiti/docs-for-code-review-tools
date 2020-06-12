Pattern: Model not deriving from `ApplicationRecord`

Issue: -

## Description

This rule checks that models subclass `ApplicationRecord` with Rails 5.0.

## Examples

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

* [RuboCop - Rails/ApplicationRecord](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsapplicationrecord)
