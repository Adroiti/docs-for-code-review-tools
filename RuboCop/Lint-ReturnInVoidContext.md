Pattern: `return` in void context

Issue: -

## Description

This rule checks for the use of a `return `with a value in a context
where the value will be ignored (initialize and setter methods).

## Examples

```ruby
# bad
def initialize
  foo
  return :qux if bar?
  baz
end

def foo=(bar)
  return 42
end
```
```ruby
# good
def initialize
  foo
  return if bar?
  baz
end

def foo=(bar)
  return
end
```

## Further Reading

* [RuboCop - Lint/ReturnInVoidContext](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintreturninvoidcontext)
