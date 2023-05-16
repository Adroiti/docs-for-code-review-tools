Pattern: Missing test case for test class

Issue: -

## Description

Checks if test class contains any test cases.

## Examples

``` ruby
# bad
class FooTest < Minitest::Test
  def do_something
  end
end

# good
class FooTest < Minitest::Test
  def test_something
    assert true
  end
end
```