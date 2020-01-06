Pattern: Suppressed `rescue`

Issue: -

## Description

This rule checks for `rescue` blocks with no body.

## Examples

```ruby
# bad

def some_method
  do_something
rescue
  # do nothing
end
```
```ruby
# bad

begin
  do_something
rescue
  # do nothing
end
```
```ruby
# good

def some_method
  do_something
rescue
  handle_exception
end
```
```ruby
# good

begin
  do_something
rescue
  handle_exception
end
```

## Further Reading

* [RuboCop - Lint/SuppressedException](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintemptyexception)
* [https://github.com/bbatsov/ruby-style-guide#dont-hide-exceptions](https://github.com/bbatsov/ruby-style-guide#dont-hide-exceptions)
