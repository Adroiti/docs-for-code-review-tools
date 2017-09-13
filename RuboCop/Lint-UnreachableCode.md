Pattern: Lint/UnreachableCode

Issue: -

## Description

This cop checks for unreachable code.
The check are based on the presence of flow of control
statement in non-final position in *begin*(implicit) blocks.

### Example

```ruby
# bad

def some_method
  return
  do_something
end

# bad

def some_method
  if cond
    return
  else
    return
  end
  do_something
end
```
```ruby
# good

def some_method
  do_something
end
```

## Further Reading

* [RuboCop - Lint/UnreachableCode](https://rubocop.readthedocs.io/en/latest/cops_lint/#lintunreachablecode)
