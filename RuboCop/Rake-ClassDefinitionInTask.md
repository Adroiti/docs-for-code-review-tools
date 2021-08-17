Pattern: Class definition in rake task

Issue: -

## Description

Detects class or module definition in a task or namespace, because it is defined to the top level. It is confusing because the scope looks in the task or namespace, but actually it is defined to the top level.

## Examples

```ruby
# bad
task :foo do
  class C
  end
end

# bad
namespace :foo do
  module M
  end
end

# good - It is also defined to the top level,
#        but it looks expected behavior.
class C
end
task :foo do
end
```

## Further Reading

* [RuboCop - Rake/ClassDefinitionInTask](https://github.com/rubocop/rubocop-rake/blob/master/lib/rubocop/cop/rake/class_definition_in_task.rb)
