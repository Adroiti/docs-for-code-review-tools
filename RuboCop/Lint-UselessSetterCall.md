Pattern: Useless setter call

Issue: -

## Description

This rule checks for setter call to local variable as the final expression of a function definition.

## Examples

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

* [RuboCop - Lint/UselessSetterCall](https://docs.rubocop.org/rubocop/cops_lint.html#lintuselesssettercall)
