Pattern: Lint/UselessSetterCall

Issue: -

## Description

This cop checks for setter call to local variable as the final
expression of a function definition.

### Example

```ruby
# bad

def something
  x = Something.new
  x.attr = 5
end
```
```ruby
# good

def something
  x = Something.new
  x.attr = 5
  x
end
```

## Further Reading

* [RuboCop - Lint/UselessSetterCall](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintuselesssettercall)
