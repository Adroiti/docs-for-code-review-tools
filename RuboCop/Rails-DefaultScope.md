Pattern: Use of `default_scope`

Issue: -

## Description

This rule looks for uses of `default_scope`.

## Examples

```ruby
# bad
default_scope -> { where(hidden: false) }

# good
scope :published, -> { where(hidden: false) }

# bad
def self.default_scope
  where(hidden: false)
end

# good
def self.published
  where(hidden: false)
end
```

## Further Reading

* [RuboCop - Rails/DefaultScope](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdefaultscope)
