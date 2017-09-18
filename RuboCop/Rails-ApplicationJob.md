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

* [RuboCop - Rails/ApplicationJob](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsapplicationjob)
