Pattern: Mutating class/module attribute

Issue: -

## Description

Avoid mutating class and module attributes. They are implemented by class variables, which are not thread-safe.

## Examples

```ruby
# bad
class User
  cattr_accessor :current_user
end
```

## Further Reading

* [RuboCop - ThreadSafety/ClassAndModuleAttributes](https://github.com/covermymeds/rubocop-thread_safety/blob/master/lib/rubocop/cop/thread_safety/class_and_module_attributes.rb)
