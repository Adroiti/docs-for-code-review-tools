Pattern: Use of Active Support load hook

Issue: -

## Description

Checks for Rails framework classes that are patched directly instead of using Active Support load hooks. Direct
patching forcibly loads the framework referenced, using hooks defers loading until it's actually needed.

## Examples

```ruby
# bad
ActiveRecord::Base.include(MyClass)

# good
ActiveSupport.on_load(:active_record) { include MyClass }
```

## Further Reading

* [Rails - Rails/ActiveSupportOnLoad](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsactivesupportonload)
* https://api.rubyonrails.org/classes/ActiveSupport/LazyLoadHooks.html
* https://guides.rubyonrails.org/engines.html#available-load-hooks