Pattern: Useless assignment

Issue: -

## Description

This rule checks for every useless assignment to local variable in every scope.
The basic idea for this rule was from the warning of `ruby -cw`:

  assigned but unused variable - foo


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
