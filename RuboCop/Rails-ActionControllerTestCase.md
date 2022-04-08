Pattern: Use of `ActionController::TestCase`

Issue: -

## Description

Using `ActionController::TestCase` is discouraged and should be replaced by
`ActionDispatch::IntegrationTest`. Controller tests are too close to the
internals of a controller whereas integration tests mimic the browser/user.

## Examples

```ruby
# bad
class MyControllerTest < ActionController::TestCase
end

# good
class MyControllerTest < ActionDispatch::IntegrationTest
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
SafeAutocorrect | `false` | Boolean
Include | `+**/test/**/*.rb+` | Array

## Further Reading

* [Rails - Rails/ActionControllerTestCase](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsactioncontrollertestcase)