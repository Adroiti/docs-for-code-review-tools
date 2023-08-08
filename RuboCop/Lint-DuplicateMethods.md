Pattern: Duplicate method definition

Issue: -

## Description

This rule checks for duplicated instance (or singleton) method definitions.

## Examples

```ruby
# bad

def duplicated
  1
end

def duplicated
  2
end
```
```ruby
# bad

def duplicated
  1
end

alias duplicated other_duplicated
```
```ruby
# good

def duplicated
  1
end

def other_duplicated
  2
end
```

## Further Reading

* [RuboCop - Lint/DuplicateMethods](https://docs.rubocop.org/rubocop/cops_lint.html#lintduplicatemethods)
