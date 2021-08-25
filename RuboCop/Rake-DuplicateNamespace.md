Pattern: Duplicate namespace

Issue: -

## Description

If namespaces are defined with the same name, Rake executes the both namespaces in definition order. It is redundant. You should squash them into one definition.

## Examples

```ruby
# bad
namespace :foo do
  task :bar do
  end
end
namespace :foo do
  task :hoge do
  end
end

# good
namespace :foo do
  task :bar do
  end
  task :hoge do
  end
end
```

## Further Reading

* [RuboCop - Rake/DuplicateNamespace](https://github.com/rubocop/rubocop-rake/blob/master/lib/rubocop/cop/rake/duplicate_namespace.rb)
