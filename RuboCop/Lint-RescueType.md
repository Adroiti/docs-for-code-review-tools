Pattern: Wrong `rescue` argument

Issue: -

## Description

Check for arguments to `rescue` that will result in a `TypeError` if an exception is raised.

## Examples

```ruby
# bad
begin
  bar
rescue nil
  baz
end

# bad
def foo
  bar
rescue 1, 'a', "#{b}", 0.0, [], {}
  baz
end

# good
begin
  bar
rescue
  baz
end

# good
def foo
  bar
rescue NameError
  baz
end
```

## Further Reading

* [RuboCop - Lint/RescueType](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintrescuetype)
