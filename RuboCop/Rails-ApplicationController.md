Pattern: Missing use of `ApplicationController`

Issue: -

## Description

Checks that controllers subclass `ApplicationController`.

## Examples

```ruby
# good
class CustomController < ApplicationController
  # ...
end

# bad
class CustomController < ActionController::Base
  # ...
end
```

## Further Reading

* [RuboCop - Rails/ApplicationController](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails)
