Pattern: Lint/EndInMethod

Issue: -

## Description

This cop checks for END blocks in method definitions.

### Example

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
