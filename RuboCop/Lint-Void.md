Pattern: Use in void context

Issue: -

## Description

This rule checks for operators, variables and literals used
in void context.

## Examples

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

* [RuboCop - Lint/Void](https://docs.rubocop.org/rubocop/cops_lint.html#lintvoid)
