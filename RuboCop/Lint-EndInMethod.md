Pattern: Use of `END` in method definition

Issue: -

## Description

This rule checks for `END` blocks in method definitions.

## Examples

```ruby
# bad

def some_method
  END { do_something }
end
```
```ruby
# good

def some_method
  at_exit { do_something }
end
```
```ruby
# good

# outside defs
END { do_something }
```

## Further Reading

* [RuboCop - Lint/EndInMethod](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintendinmethod)
