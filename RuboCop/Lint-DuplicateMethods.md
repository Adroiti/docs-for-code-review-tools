Pattern: Lint/DuplicateMethods

Issue: -

## Description

This cop checks for duplicated instance (or singleton) method
definitions.

### Example

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

* [RuboCop - Lint/DuplicateMethods](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintduplicatemethods)
