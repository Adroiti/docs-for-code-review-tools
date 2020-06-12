Pattern: Overriding built-in _Active Record_ method

Issue: -

## Description

Checks for overriding built-in Active Record methods instead of using callbacks.

## Examples

```ruby
# bad
class Book < ApplicationRecord
  def save
    self.title = title.upcase!
    super
  end
end

# good
class Book < ApplicationRecord
  before_save :upcase_title

  def upcase_title
    self.title = title.upcase!
  end
end
```

## Configurable attributes

Name | Default value
--- | ---
Include | `app/models/**/*.rb`

## Further Reading

* [RuboCop - Rails/ActiveRecordOverride](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsactiverecordoverride)
