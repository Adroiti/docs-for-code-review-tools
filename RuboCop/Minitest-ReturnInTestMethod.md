Pattern: Use of `return` in test method

Issue: -

## Description

Enforces the use of `skip` instead of `return` in test methods.

## Examples

``` ruby
# bad
def test_something
  return if condition?
  assert_equal(42, something)
end

# good
def test_something
  skip if condition?
  assert_equal(42, something)
end
```

## Further Reading

-   <https://minitest.rubystyle.guide/#skipping-runnable-methods>