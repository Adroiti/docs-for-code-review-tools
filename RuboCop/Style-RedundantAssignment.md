Pattern: Redundant assignment before returning

Issue: -

## Description

Checks for redundant assignment before returning.

## Examples

```ruby
# bad
def test
  x = foo
  x
end

# bad
def test
  if x
    z = foo
    z
  elsif y
    z = bar
    z
  end
end

# good
def test
  foo
end

# good
def test
  if x
    foo
  elsif y
    bar
  end
end
```

## Further Reading

* [RuboCop - Style/RedundantAssignment](https://docs.rubocop.org/rubocop/cops_style.html#styleredundantassignment)
