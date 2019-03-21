Pattern: Malformed options for `skip_*`

Issue: -

## Description

The `if` option will be ignored when `if` and `only` are used together. Similarly, the `except` option will be ignored when `if` and `except` are used together.

## Examples

```ruby
# bad
class MyPageController < ApplicationController
  skip_before_action :login_required,
    only: :show, if: :trusted_origin?
end

# good
class MyPageController < ApplicationController
  skip_before_action :login_required,
    if: -> { trusted_origin? && action_name == "show" }
end
```
```ruby
# bad
class MyPageController < ApplicationController
  skip_before_action :login_required,
    except: :admin, if: :trusted_origin?
end

# good
class MyPageController < ApplicationController
  skip_before_action :login_required,
    if: -> { trusted_origin? && action_name != "admin" }
end
```

## Configurable attributes

Name | Default value
--- | --- | ---
Include | `app/controllers/**/*.rb`

## Further Reading

* [RuboCop - Rails/IgnoredSkipActionFilterOption](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsignoredskipactionfilteroption)