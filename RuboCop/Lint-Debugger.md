Pattern: Call to `debugger`/`pry`

Issue: -

## Description

This rule checks for calls to `debugger` or `pry`.

## Examples

```ruby
# bad (ok during development)

# using pry
def some_method
  binding.pry
  do_something
end
```
```ruby
# bad (ok during development)

# using byebug
def some_method
  byebug
  do_something
end
```
```ruby
# good

def some_method
  do_something
end
```

## Further Reading

* [RuboCop - Lint/Debugger](https://docs.rubocop.org/rubocop/cops_lint.html#lintdebugger)
