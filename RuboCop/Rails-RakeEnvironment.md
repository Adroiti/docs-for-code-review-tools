Pattern: Missing `:environment` for Rake task

Issue: -

## Description

This cop checks for Rake tasks without the `:environment` task
dependency. The `:environment` task loads application code for other
Rake tasks. Without it, tasks cannot make use of application code like
models.

You can ignore the offense if the task satisfies at least one of the
following conditions:
* The task does not need application code.
* The task invokes the `:environment` task.

## Examples

```ruby
# bad
task :foo do
  do_something
end

# good
task foo: :environment do
  do_something
end
```

## Further Reading

* [RuboCop - Rails/RakeEnvironment](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails)
