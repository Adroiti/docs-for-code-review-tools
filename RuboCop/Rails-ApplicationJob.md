Pattern: Job not deriving from `ApplicationJob`

Issue: -

## Description

This rule checks that jobs subclass `ApplicationJob` with Rails 5.0.

## Examples

```ruby
# good
class Rails5Job < ApplicationJob
  ...
end

# bad
class Rails4Job < ActiveJob::Base
  ...
end
```

## Further Reading

* [RuboCop - Rails/ApplicationJob](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsapplicationjob)
