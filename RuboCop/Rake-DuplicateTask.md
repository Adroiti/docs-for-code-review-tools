Pattern: Duplicate task

Issue: -

## Description

If tasks are defined with the same name, Rake executes the both tasks in definition order. It is misleading sometimes. You should squash them into one definition.

## Examples

```ruby
# bad
task :foo do
  p 'foo 1'
end
task :foo do
  p 'foo 2'
end

# good
task :foo do
  p 'foo 1'
  p 'foo 2'
end
```

## Further Reading

* [RuboCop - Rake/DuplicateTask](https://github.com/rubocop/rubocop-rake/blob/master/lib/rubocop/cop/rake/duplicate_task.rb)
