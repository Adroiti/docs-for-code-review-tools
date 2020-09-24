Pattern: Wrong Active Record callback order

Issue: -

## Description

This rule checks that Active Record callbacks are declared in the order in which they will be executed.

## Examples

```ruby
# bad
class Person < ApplicationRecord
  after_commit :after_commit_callback
  before_validation :before_validation_callback
end

# good
class Person < ApplicationRecord
  before_validation :before_validation_callback
  after_commit :after_commit_callback
end
```

## Further Reading

* [RuboCop - Rails/ActiveRecordCallbacksOrder](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsactiverecordcallbacksorder)
