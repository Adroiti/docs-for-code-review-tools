Pattern: Rescuing `Exception` class

Issue: -

## Description

This rule checks for `rescue` blocks targeting the Exception class.

## Examples

```ruby
# bad

begin
  do_something
rescue Exception
  handle_exception
end
```
```ruby
# good

begin
  do_something
rescue ArgumentError
  handle_exception
end
```

## Further Reading

* [RuboCop - Lint/RescueException](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintrescueexception)
* [https://github.com/bbatsov/ruby-style-guide#no-blind-rescues](https://github.com/bbatsov/ruby-style-guide#no-blind-rescues)
