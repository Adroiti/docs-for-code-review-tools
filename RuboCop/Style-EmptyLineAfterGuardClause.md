Pattern: Missing empty line after guard clause

Issue: -

## Description

This rule enforces empty line after guard clause

## Examples

```ruby
# bad
def foo
  return if need_return?
  bar
end

# good
def foo
  return if need_return?

  bar
end

# good
def foo
  return if something?
  return if something_different?

  bar
end

# also good
def foo
  if something?
    do_something
    return if need_return?
  end
end
```

## Further Reading

* [RuboCop - Style/EmptyLineAfterGuardClause](https://docs.rubocop.org/rubocop/cops_style.html#styleemptylineafterguardclause)
