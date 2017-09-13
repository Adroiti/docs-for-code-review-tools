Pattern: Lint/Void

Issue: -

## Description

This cop checks for operators, variables and literals used
in void context.

### Example

```ruby
# bad

def some_method
  some_num * 10
  do_something
end
```
```ruby
# bad

def some_method(some_var)
  some_var
  do_something
end
```
```ruby
# good

def some_method
  do_something
  some_num * 10
end
```
```ruby
# good

def some_method(some_var)
  do_something
  some_var
end
```

## Further Reading

* [RuboCop - Lint/Void](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintvoid)
