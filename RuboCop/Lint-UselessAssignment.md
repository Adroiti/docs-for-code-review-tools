Pattern: Useless assignment

Issue: -

## Description

Use `_` to prefix unused block parameters and local variables. It's also acceptable to use just `_` (although it's a bit less descriptive). This convention is recognized by the Ruby interpreter and tools like RuboCop and will suppress their unused variable warnings.

## Examples

```ruby
# bad

def some_method
  some_var = 1
  do_something
end
```
```ruby
# good

def some_method
  some_var = 1
  do_something(some_var)
end
```

## Further Reading

* [RuboCop - Lint/UselessAssignment](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintuselessassignment)
* [https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars](https://github.com/bbatsov/ruby-style-guide#underscore-unused-vars)
