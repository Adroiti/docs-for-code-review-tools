Pattern: Unnecessary rescue

Issue: -

## Description

Checks for useless `rescue`s, which only re-raise rescued exceptions.

## Examples

```ruby
# bad
def foo
  do_something
rescue
  raise
end

# bad
def foo
  do_something
rescue => e
  raise # or 'raise e', or 'raise $!', or 'raise $ERROR_INFO'
end

# good
def foo
  do_something
rescue
  do_cleanup
  raise
end

# bad (latest rescue)
def foo
  do_something
rescue ArgumentError
  # noop
rescue
  raise
end

# good (not the latest rescue)
def foo
  do_something
rescue ArgumentError
  raise
rescue
  # noop
end
```

## Further Reading

* [RuboCop - Lint/UselessRescue](https://docs.rubocop.org/rubocop/cops_lint.html#lintuselessrescue)
