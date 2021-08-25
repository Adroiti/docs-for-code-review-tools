Pattern: Missing use of `desc` method

Issue: -

## Description

Rake task definition should have a description with `desc` method.
It is useful as a documentation of task. And Rake does not display
task that does not have `desc` by `rake -T`.

## Examples

```ruby
# bad
task :do_something

# bad
task :do_something do
end

# good
desc 'Do something'
task :do_something

# good
desc 'Do something'
task :do_something do
end
```

## Further Reading

* [RuboCop - Rake/Desc](https://github.com/rubocop/rubocop-rake/blob/master/lib/rubocop/cop/rake/desc.rb)
