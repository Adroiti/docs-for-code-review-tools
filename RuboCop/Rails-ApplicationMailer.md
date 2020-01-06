Pattern: Missing use of `ApplicationMailer`

Issue: -

## Description

Checks that mailers subclass ApplicationMailer with Rails 5.0.

## Examples

```ruby
# good
class CustomMailer < ApplicationMailer
  # ...
end
      #
# bad
class CustomMailer < ActionMailer::Base
  # ...
end
```

## Further Reading

* [RuboCop - Rails/ApplicationMailer](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails)
